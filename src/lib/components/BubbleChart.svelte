<script lang="ts">
    import { onMount } from "svelte";
    import * as d3 from "d3";
    
    let el;

    onMount(async () => {
        const data = await d3.csv("/leaderboard.csv", function (d: any) {
            return {
                contributor: d["Contributor"],
                sections: d["Sections"],
                submissionCount: d["Submissions"],
                quality: d["Overall quality"],
                score: d["Score"]
            } as {contributor: string, submissionCount: number, quality: number, score: number}
        })

        const height = 500;
        const svg = d3.select(el)
            .append("svg")
            .attr('height', height)
            .attr("width", "100%")
            .append("g");

        const radiusScale = d3.scaleSqrt().domain([1, 1200]).range([10, 90])
        const contribColor = q => q == 20 ? "#ffd700" : "#70baec";

        const Tooltip = d3.select(el)
            .append("div")
            .style("opacity", 0)
            .attr("class", "tooltip")
            .style("background-color", "white")
            .style("border", "solid")
            .style("border-width", "2px")
            .style("border-radius", "5px")
            .style("position", "absolute")
            .style("padding", "5px")

        const mouseover = (e: any, d: any) => Tooltip.style("opacity", 1);
        const mousemove = (e: any, d: any) =>
            Tooltip.html(`<u>${d.contributor}</u>
            <br>Sections contributed to: ${d.sections}
            <br>Total submissions: ${d.submissionCount}
            <br>Overall quality score (out of 20): ${d.quality}
            <br>Overall contribution score: ${d.score}`)
                .style("left", `${e.x + window.pageXOffset + 2}px`)
                .style("top", `${e.y + window.pageYOffset + 10}px`);
        const mouseleave = (e: any, d: any) => Tooltip.style("opacity", 0);
            

        const node = svg
            .selectAll("circle")
            .data(data)
            .join("circle")
            .attr("r", d => radiusScale(d.score))
            .style("fill", d => contribColor(d.quality))
            .style("fill-opacity", 0.3)
            .attr("stroke", d => contribColor(d.quality))
            .style("stroke-width", 4)
            .on("mouseover", mouseover)
            .on("mousemove", mousemove)
            .on("mouseleave", mouseleave);
            
        const texts = svg.selectAll(null)
            .data(data)
            .enter()
            .append("text")
            .text(d => d.contributor.split(" ").map(s => s.slice(0, 1)).join(""))
            .attr("color", "white")
            .attr("font-size", d => `${radiusScale(d.score) - 15}px`)
            .attr("text-anchor", "middle")
            .attr("dominant-baseline", "middle");

        function drawChart() {
            const width = parseInt(d3.select(el).style("width"), 10);
            const simulation = d3.forceSimulation()
                .force("center", d3.forceCenter().x(width/2).y(height/2))
                .force("charge", d3.forceManyBody().strength(0.5))
                .force("collide", d3.forceCollide().strength(0.1).radius(d => radiusScale((d as any).score)).iterations(1));

            simulation.nodes(data as any).on("tick", function (d: any) {
                node.attr("cx", d=>(d as any).x).attr("cy", d=>(d as any).y);
                texts.attr("x", d=>(d as any).x).attr("y", d=>(d as any).y);
            } as any)
        }
        
        drawChart();
        window.addEventListener('resize', drawChart);
    });
</script>

<div bind:this={el} class="chart"></div>