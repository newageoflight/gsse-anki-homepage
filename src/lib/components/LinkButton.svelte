<script lang="ts">
    export let href: string;
    export let inHeader: boolean = false;
</script>

<a href={href} class="{inHeader ? 'in-header' : ''}"><slot></slot></a>

<style>
    a {
        appearance: button;
        text-decoration: none;
        color: white;
        background-color: #0075e0;
        border-radius: 5px;
        padding: 0.5em;
        margin-right: 0.25em;
    }

    .in-header {
        font-size: 1.5rem;
        /* margin: 0 0.75rem 0.5rem 0; */
        /* padding: 0.5rem 1rem; */
    }
    
    a:hover {
        background-color: #66acec;
    }

    a:active {
        background-color: #99c8f3;
    }
</style>