<script lang="ts">
    import IconLinkButton from "./IconLinkButton.svelte";

    type Status = "nonrelease" | "prerelease" | "public";
    export let status: Status;
    export let link: string = undefined;
</script>
<!--
    Some details first.

    A subdeck for download can either be:
    - Non-release i.e. not available because it's not finished.
    - Pre-release i.e. available only to approved pre-testers.
    - Public i.e. available to the general public
-->

<div class="row">
    <div class="content">
        <slot></slot>
    </div>
    <div class="actions">
        {#if status === "public"}
            <IconLinkButton href={link} icon="carbon:download" />
        {:else if status === "prerelease"}
            <IconLinkButton href="#" disabled icon="fluent:presence-blocked-10-regular" alt="Approved pre-testers only" />
        {:else if status === "nonrelease"}
            <IconLinkButton href="#" disabled icon="clarity:no-access-solid" alt="Not available" />
        {/if}
    </div>
</div>

<style>
    .row {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    
    .actions {
        display: flex;
        align-items: center;
        flex-direction: row;
    }
</style>