<script lang="ts">
    import BubbleChart from "./components/BubbleChart.svelte";

</script>

<div id="contributors">
    <h1>Credits</h1>
    <section>
        <div class="section-text">
            Founder/Project Manager/Content Auditor and Editor: Christopher Chen
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
        <p>Vivian Lin, Ryan Ting, Nicholas Kesby</p>
    </section>
</div>

<style>
    #contributors {
        padding: 1rem 5rem;
        background-color: #eee;
    }
</style>