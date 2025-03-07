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
<style>:root {
  --color-accent: oklch(65% 50% 0); /* Primary accent color in OKLCH format */
  /* --border-gray: oklch(80% 3% 200); Gray for borders */

  /* ADD the rest of the color definitions here if needed! */
}
html {
  --color-accent: oklch(65% 50% 0); /* Accent color */
  accent-color: var(--color-accent); /* Apply accent globally */
  color-scheme: light dark;
  color-scheme: light;
  color-scheme: dark;
}

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
body {
  font: 100%/1.5 system-ui; /* 100% font size, 1.5 line height, system font. Same as in lab 1 */
  max-width: 45rem; /* Limits width to 50 rems for better readability */
  /* Add here margin-inline */
  margin-inline: max(1em, (100% - 100ch) / 2);
  /* Add here padding around the body */
  padding: 20px; /* Applies 20px to top, right, bottom, and left */
}

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
input,
textarea,
button {
  font: inherit; /* Ensures form elements use the same font as the body */
}

/* Step 3.2: Top-down layout */

input,
textarea,
button {
  /* We define the elements in which we want this to take effect */
  display: block;
  width: 100%;
  /* box-sizing: border-box; */
  margin-block: 0em;
  padding: 0.5em;
  margin-bottom: 0.5em;
  font-size: 1em;
  /* add width here*/
  /* add box-sizing here */
}
label {
  /* We'll add the spacing between labels here */
  margin-block: 0em;
  /* display: block; */
  /* font-weight: bold; */
}

/* Step 3.2: Grid layout */

form {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: 1em;
  padding: 1em;
  width: 100%;
}

label {
  display: grid;
  grid-template-columns: subgrid;
  grid-column: 1 / -1;
}

input,
button {
  grid-column: 2;
  padding: 0.5em;
  font-size: 1em;
}

button {
  grid-column: 1 / -1;
  padding: 0.75em;
  /* background-color: #d0d2d0; */
  /* color: white; */
  border: none;
  cursor: pointer;
  font-size: 1em;
}

button:hover {
  background-color: #45a049;
}
/* 
        Please work on grid layout here.
        NOTE: this will override what you did in the previous step! remember *Specificity*
    */

/* STEP 4: Style your projects page */
/* Global styles */
/* Global image constraints */
img {
  max-width: 100%;
  height: auto;
}

/* Enhanced typography for headings */
h1,
h2,
h3,
h4,
h5,
h6 {
  line-height: 1.1;
  text-wrap: balance;
}

h1 {
  font-size: 400%;
  margin-bottom: 1em;
}

h2 {
  margin: 0;
}

/* Projects grid layout */
.projects {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(15em, 1fr));
  gap: 2rem;
  padding: 1rem;
}

/* Article subgrid layout */
.projects article {
  display: grid;
  grid-template-rows: subgrid;
  grid-row: span 3;
}

/* Base styling for articles */
.projects article {
  border-radius: 8px;
  padding: 1rem;
  transition: transform 0.2s ease;
}

.projects article:hover {
  transform: translateY(-4px);
}

/* Article content styling */
.projects article img {
  width: 100%;
  object-fit: cover;
  border-radius: 4px;
}

.projects article p {
  margin: 1rem 0;
  line-height: 1.5;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  h1 {
    font-size: 300%;
  }

  .projects {
    gap: 1rem;
  }
} /* Global image constraints */
img {
  max-width: 100%;
  height: auto;
}

/* Enhanced typography for headings */
h1,
h2,
h3,
h4,
h5,
h6 {
  line-height: 1.1;
  text-wrap: balance;
}

h1 {
  font-size: 400%;
  margin-bottom: 1em;
}

h2 {
  margin: 0;
}

/* Projects grid layout */
.projects {
  display: grid;
  /* Set a fixed column width that results in 3 columns at full width */
  grid-template-columns: repeat(auto-fit, minmax(calc(33.333% - 2rem), 1fr));
  gap: 2rem;
  padding: 1rem;
  max-width: 100%;
  margin: 0 auto;
}

/* Article subgrid layout */
.projects article {
  display: grid;
  grid-template-rows: subgrid;
  grid-row: span 3;
}

/* Base styling for articles */
.projects article {
  border-radius: 8px;
  padding: 1rem;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease;
}

.projects article:hover {
  transform: translateY(-4px);
}

/* Article content styling */
.projects article img {
  width: 100%;
  object-fit: cover;
  border-radius: 4px;
}

.projects article p {
  margin: 1rem 0;
  line-height: 1.5;
}

/* Responsive adjustments */
@media (max-width: 900px) {
  .projects {
    /* Switch to 2 columns */
    grid-template-columns: repeat(auto-fit, minmax(calc(50% - 2rem), 1fr));
  }

  h1 {
    font-size: 300%;
  }
}

@media (max-width: 600px) {
  .projects {
    /* Switch to 1 column */
    grid-template-columns: 1fr;
    gap: 1rem;
  }
}

/* STEP 5: Style your CV */

/* HINT: one thing you could do here is define an ID selector in your resume/index.html -> <section id="resume"> 
             and then you can generate a layour just for your resume
             For example:
    */
/* Global styles */
/* Global styles */
body {
  font-family: "Inter", -apple-system, BlinkMacSystemFont, sans-serif;
  max-width: 1000px;
  margin: 0 auto;
  padding: 2rem;
  line-height: 1.6;
  /* background-color: #f5f5f5; */
}

/* Navigation styles */
nav {
  /* background-color: #f8f9fa; */
  padding: 1rem;
  /* border-radius: 8px; */
  margin-bottom: 2rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  /* border: 1px solid #e0e0e0; */
}

nav a {
  /* color: #555; */
  text-decoration: none;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  transition: background-color 0.2s;
}

/* Header styles */
header {
  /* background-color: white; */
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
  margin-bottom: 2rem;
  border: 1px solid #e0e0e0;
}

h1 {
  /* color: #333; */
  margin: 0 0 1rem 0;
  font-size: 2.5rem;
  border-bottom: 2px solid #e0e0e0;
  padding-bottom: 0.5rem;
}

header p {
  margin: 0.5rem 0;
}

/* Section styles */
section {
  /* background-color: white; */
  padding: 2rem;
  border-radius: 8px;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.05);
  margin-bottom: 2rem;
  border: 1px solid #e0e0e0;
}

h2 {
  /* color: #444; */
  margin: 0 0 1.5rem 0;
  font-size: 1.8rem;
}

h3 {
  /* color: #555; */
  margin: 0 0 0.5rem 0;
  font-size: 1.4rem;
}

/* Article styles */
article {
  margin-bottom: 2rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid #eee;
}

article:last-child {
  margin-bottom: 0;
  padding-bottom: 0;
  border-bottom: none;
}

article header {
  background: none;
  padding: 0;
  box-shadow: none;
  margin-bottom: 1rem;
  border: none;
}

/* List styles */
ul {
  padding-left: 1.5rem;
  margin: 0.5rem 0;
}

li {
  margin-bottom: 0.5rem;
}

/* Link styles */
a {
  /* color: #666; */
  text-decoration: none;
  transition: color 0.2s;
}

/* a:hover {
  color: #333;
} */

/* Time element styles */
/* time {
  color: #777;
} */

/* Strong element styles */
/* strong {
  color: #555;
} */

/* Responsive design */
@media (max-width: 768px) {
  body {
    padding: 1rem;
  }

  nav {
    flex-direction: column;
    align-items: center;
  }

  nav a {
    width: 100%;
    text-align: center;
  }

  header,
  section {
    padding: 1.5rem;
  }

  h1 {
    font-size: 2rem;
  }

  h2 {
    font-size: 1.5rem;
  }

  h3 {
    font-size: 1.2rem;
  }
}
#resume {

  max-width: 10rem;
}
</style>