<script lang="ts">
    import Contributors from './lib/Contributors.svelte';
    import Downloads from './lib/Downloads.svelte';
    import Footer from './lib/Footer.svelte';
    import Header from './lib/Header.svelte';
    import JoinUs from './lib/JoinUs.svelte';
import ReportIssues from './lib/ReportIssues.svelte';
</script>

<main>
    <Header />
    <Downloads />
    <Contributors />
    <JoinUs />
    <ReportIssues />
    <Footer />
</main>

<style>
    :root {
        font-family: 'Helvetica Neue', Arial, Helvetica, sans-serif;
    }

    :global(html, body, #app) {
        margin: 0;
    }
</style>
