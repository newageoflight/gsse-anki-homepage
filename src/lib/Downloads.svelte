<script>
import DownloadRow from "./components/DownloadRow.svelte";

</script>
<div id="downloads">
    <h1>Downloads</h1>
    <h2>Entire deck</h2>
    <p>Not yet available.</p>
    <h2>In parts</h2>
    <ol>
        <li><DownloadRow link="#" status="prerelease">Introduction to regional anatomy (50% complete)</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Upper limb</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Lower limb</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Thorax</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Abdomen (50% complete)</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Head, neck and spine (61% complete)</DownloadRow></li>
        <li><DownloadRow link="#" status="nonrelease">CNS (57% complete)</DownloadRow></li>
        <li><DownloadRow link="#" status="prerelease">Skull osteology (100% complete)</DownloadRow></li>
    </ol>
</div>

<style>
    #downloads {
        padding: 1rem 5rem;
    }
</style>