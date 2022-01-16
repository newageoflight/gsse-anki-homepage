<script>

import SocialIcon from "./components/IconLinkButton.svelte";
import Spacer from "./components/Spacer.svelte";

</script>
<footer>
    <div class="links">
        <SocialIcon href="https://gsse-anki.notion.site" icon="cib:notion" size="2rem" />
        <Spacer width="0.5rem" />
        <SocialIcon href="https://github.com/newageoflight/gsse-anki" icon="cib:github" size="2rem" />
        <Spacer width="0.5rem" />
        <SocialIcon href="https://www.facebook.com/groups/1300364850298639" icon="cib:facebook" size="2rem" />
    </div>
    <p>Copyright &copy; 2020- Anki for GSSE team</p>
    <p>Website design by <a href="https://github.com/newageoflight">Christopher Chen</a></p>
</footer>

<style>
    footer {
        padding: 1rem 5rem;
        background-color: #001749;
        color: white;
        text-align: center;
    }
    
    footer a {
        color: white;
    }
</style>