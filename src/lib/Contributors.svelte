<script lang="ts">
    import BubbleChart from "./components/BubbleChart.svelte";

</script>

<div id="contributors">
    <h1>Credits</h1>
    <section>
        <div class="section-text">
            Founder/Project Manager/Content Auditor and Editor: Christopher Chen
            <br/>
            Note: I'm a bit busy with my current terms so I won't be able to actively contribute to this project. 
            If you're interested in helping out with the coordination/management of this project, 
            please email me at <a href="mailto:camint3rnal@live.com">camint3rnal@live.com</a> or message me on Facebook.
        </div>
        <div class="section-image">
            <div class="avatar"></div>
        </div>
    </section>
    <section>
        <h2>Content contributors</h2>
        <BubbleChart />
    </section>
    <section>
        <h2>Testers</h2>
        <p>Vivian Lin, Ryan Ting, Bridget Hwang, Will Karantanis, Nicholas Kesby, Hayden Ly</p>
    </section>
</div>

<style>
    #contributors {
        padding: 1rem 5rem;
        background-color: #eee;
    }
</style>
