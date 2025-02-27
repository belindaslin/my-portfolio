<!-- <Project data={project} /> -->

<script>
    export let hLevel = 2;
    export let data = {}; // Receive project data as a prop
</script>

<article>
    <svelte:element this={"h" + hLevel}>{data.title}</svelte:element>
    <img src={data.image} alt={data.title} />
    <p>{data.description}</p>
</article>