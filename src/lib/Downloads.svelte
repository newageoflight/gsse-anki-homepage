<script>
import DownloadRow from "./components/DownloadRow.svelte";

</script>
<div id="downloads">
    <h1>Downloads</h1>
    <p>Finalised versions of the deck are made available here.</p>
    <h2>Entire deck</h2>
    <p>Not yet available.</p>
    <h2>In parts</h2>
    <ol>
        <li><DownloadRow link="https://mega.nz/file/H0EB0IJD#ubi7nWBv2keN5Y1bv5OJ4kqqtW9BcxmJdaIbdPS-vq0" status="public">Introduction to regional anatomy (50% complete)</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Upper limb</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Lower limb</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Thorax</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Abdomen (95% complete)</DownloadRow></li>
        <li><DownloadRow link="#" status="nonrelease">Head, neck and spine (61% complete)</DownloadRow></li>
        <li><DownloadRow link="#" status="nonrelease">CNS (57% complete)</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Skull osteology</DownloadRow></li>
    </ol>
</div>

<style>
    #downloads {
        padding: 1rem 5rem;
    }
</style>
