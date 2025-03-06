<script>
  import projects from "$lib/projects.json";
  import Project from "$lib/Project.svelte";
  let profileData = fetch("https://api.github.com/users/your-username");
</script>
 


<!-- {#each projects.slice(0, 3) as p}
<Project data={p} />
{/each} -->

<!-- <h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
<body> -->
    <!-- Start of "body" section  -->

    <!-- <h1> (Heading 1) represents the main heading of a webpage or a section.-->
    <h1>Belinda Lin</h1>
    <!-- <nav>
      <a href="index.html" class="active">Home</a>
         
      <a href="projects/index.html">Projects</a>
      
      <a href="contact/index.html">Contact</a>
      <a href="resume/index.html">Resume</a>
      <a href="https://github.com/belindaslin" target="_blank">GitHub</a>
    </nav> -->
    <!-- <p> (Paragraph) represents a paragraph of text.-->
    <p>
      Student at MIT studying Artificial Intelligence and Mathematics. Hobbies
      include tennis, reading, art
    </p>

    <!-- <img> (Image) tag is used to display images.-->
    <img src="./images/IMG_4270.jpg" alt="This is me!" width="100%" />
    <!-- Example:
            <img src="images/my_image.jpeg" alt="A description of the image">
        -->

    <!-- <nav> (Navigation) is used to create a menu with links to other pages or external sites. -->
      
    <!-- {#await fetch("https://api.github.com/users/belindaslin") }
    <p>Loading...</p>
    {:then response} {#await response.json()}
    <p>Decoding...</p>
    {:then data}
    <p>The data is { JSON.stringify(data) }</p>
    {:catch error}
    <p class="error">Something went wrong: {error.message}</p>
    {/await} {:catch error}
    <p class="error">Something went wrong: {error.message}</p>
    {/await} -->
    {#await fetch("https://api.github.com/users/belindaslin")}
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
{/await}
      <section>
          <h2>Latest Projects</h2>
          <div class="projects highlights">
              {#each projects.slice(0, 3) as p}
                  <Project data={p} hLevel={3} />
              {/each}
          </div>
      </section>
  