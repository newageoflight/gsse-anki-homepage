<script lang="ts">
    import logo from "../assets/anki-gsse.svg";
    import LinkButton from "./components/LinkButton.svelte";
</script>

<header id="header">
    <div class="description">
        <h1>Anki for GSSE</h1>
        <p>Easy, friendly flashcards for GSSE preparation</p>
        <div class="button-row">
            <LinkButton href="#downloads" inHeader>Get started</LinkButton>
            <LinkButton href="#joinus" inHeader>Join us</LinkButton>
        </div>
    </div>
    <div class="logo">
        <img src={logo} alt="Logo">
    </div>
</header>

<style>
    h1 {
        font-size: 5rem;
        margin: 0;
    }
    
    p {
        margin-top: 0;
        margin-bottom: 1rem;
    }
    
    .description {
        flex: 1;
    }
    
    /* on mobile, the logo should be above the description */
    
    header {
        display: flex;
        background: linear-gradient(45deg,  #020031 0%,#007ed8 100%);
        color: white;
        font-size: 2.5rem;
        padding: 1em 5rem;
        align-items: center;
        flex-direction: column-reverse;
    }
    
    
    .logo > img {
        height: min(80vw, 512px);
        width: min(80vw, 512px);
    }
    
    @media(min-width: 768px) {
        header {
            flex-direction: row;
        }

        .button-row {
            justify-content: flex-start;
        }

        .logo > img {
            height: 512px;
            width: 512px;
        }
    }
    
</style>