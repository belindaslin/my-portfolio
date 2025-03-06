<script>
import { page } from "$app/stores";
// let colorScheme = "light dark";

let root = globalThis?.document?.documentElement;
$: root?.style.setProperty("color-scheme", colorScheme);
let localStorage = globalThis.localStorage ?? {};
$: {
    localStorage.colorScheme = colorScheme;
    console.log("change_color")}
let colorScheme = localStorage.colorScheme ?? "light dark";

let pages = [
  { url: "./", title: "Home" },
  { url: "./projects", title: "Projects" },
  { url: "./resume", title: "Resume" },
  { url: "./contact", title: "Contact" },
  { url: "https://github.com/belindaslin", title: "Github" },

];

</script>
<!-- {
    JSON.stringify($page)
  } -->

<nav>
    {#each pages as p}
    <a
    href={p.url}
    class:current={"." + $page.route.id ===  p.url}
    target={p.url.startsWith("http") ? "_blank" : null}
    >
    {p.title}
    <!-- {p.url}
    {$page.route.id} -->
    </a>
    {/each}
</nav>
<style>
  
  
  .color-scheme {
    position: absolute;
    top: 1rem;
    right: 1rem; /* Ensures it's aligned to the right */
    display: inline-flex;
    /* align-items: center; */
    gap: 4px;
    font-size: 80%;
    font-family: inherit;
  }
  /* STEP 1: Prevent content from getting too wide */
  
  /* 
      Here we can define the base style for the body element. We already added this in Lab 1, but let's complete it!
  */
  
  /* STEP 2: Styling the navigation bar */
  
  /* 
     Step 2.1: Getting <ul> and <li> out of the way
     "display: contents" removes default styling while keeping semantic structure 
     (you do not need to make any changes here for step 2.1, but please take note of it!)
  */
  nav ul,
  nav li {
    display: contents;
  }
  
  /* Step 2.2: Apply Flexbox to the navigation */
  nav {
    display: flex; /* Turns nav into a flex container */
    border-bottom-width: 1px;
    border-bottom-style: solid;
    /* --border-color: oklch(50% 10% 200 / 40%); */
  
    --border-color: oklch(50% 10% 200 / 40%);
    margin-bottom: 3em;
  
    /* You will need to continue writing here for step 2.3 */
  }
  
  /* Step 2.3: Style navigation links for each element <a> */
  nav a {
    flex: 1; /* step 2.2 for each element to take the same space  */
    text-decoration: none; /* Remove the underline from the links by setting */
    color: inherit;
    text-align: center;
    padding: 0.5em;
    /* margin-bottom: 3em; */
  }
  /* NOTE: please make sure that in each index.html page you add class="current" to the current page*/
  /* For example:  <a href="index.html" class="current">Home</a> */
  
  nav a.current {
    border-bottom-width: 0.4em;
    border-bottom-color: var(--border-color);
    padding-bottom: 0.4em;
    border-bottom-style: solid;
    font-weight: bold;
  }
  /* Add here what your current page should look like at the navigation bar (highlight)*/
  
  /* Before jumping to the next step, remember to complete wtep 2.3 by editing 'nav' */
  
  /* 
     Step 2.4: Accent color and hover styles
  */
  
  nav a:hover {
    border-bottom-width: 4px;
    border-bottom-style: solid;
    border-bottom-color: var(--color-accent);
    padding-bottom: 0.4em;
    transition: border-color 0.3s ease;
    background-color: color-mix(in oklch, var(--color-accent), canvas 85%);
  }
  /* Add here hover effects */
  
  /*  STEP 3: Contact form layout */
  
  /* Step 3.1: Integrate typography */
  /* (you do not need to make any changes here for step 2.1, but please take note of it!) */
  
</style> 
<label class="color-scheme">
    
    <label for="theme">Theme: </label>
    <select bind:value={colorScheme} id="theme">

    
        <option value="light dark">Auto</option>
        <option value="light">Light</option>
        <option value="dark">Dark</option>
    </select>
</label>

<!-- {#await fetch("https://api.github.com/users/belindaslin")}
<p>Loading...</p>
{:then response}
{#await response.json()}
  <p>Decoding...</p>
{:then data}
  <section>
    <h2>My GitHub Stats</h2>
    <dl>
      <dt>Followers:</dt>
      <dd>{data.followers}</dd>
      <dt>Following:</dt>
      <dd>{data.following}</dd>
      <dt>Public Repositories:</dt>
      <dd>{data.public_repos}</dd>
    </dl>
  </section>
{:catch error}
  <p class="error">Something went wrong: {error.message}</p>
{/await}
{:catch error}
<p class="error">Something went wrong: {error.message}</p>
{/await} -->
<slot />