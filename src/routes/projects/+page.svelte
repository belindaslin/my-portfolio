<svelte:head>
  <title>Projects</title>
</svelte:head>


<script>
  import projects from "$lib/projects.json";
  import Project from "$lib/Project.svelte";
</script>

<h1>{projects.length} Projects </h1>
<!-- <pre>{ JSON.stringify(projects, null, "\t") }</pre> -->
    <!-- <nav>
      <a href="../index.html">Home</a>

      <a href="index.html" class="active">Projects</a>
      <a href="../contact/index.html">Contact</a>
      <a href="../resume/index.html">Resume</a>
      <a href="https://github.com/belindaslin" target="_blank">GitHub</a>
    </nav> -->
    <form>
      <section class="projects">
        <div class="projects">
          {#each projects as p}
          <Project data={p} />
          {/each}
          <!-- {#each projects as p}
          <article>
            <h2>A3</h2>
            <a href="a3.html">
              <img
                src="https://vis-society.github.io/labs/2/images/empty.svg"
                alt="Project2"
              />
            </a>
            <p>
              Cupiditate quis architecto beatae ipsam, nisi sapiente vitae at
              omnis? Quae nulla cupiditate reprehenderit veritatis inventore
              amet suscipit repudiandae delectus corrupti facilis blanditiis,
              aliquid excepturi modi unde nam odit distinctio?
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>Obcaecati minima omnis nemo?</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt="Project3"
            />
            <p>
              Quaerat iure perspiciatis ex, consequuntur ea culpa quibusdam et,
              ipsum voluptatibus totam ab rem. Ducimus impedit hic dolores
              magnam harum labore vitae, illum ipsum laborum enim ad. Officiis,
              cupiditate deleniti?
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>Dolorem fugiat dicta consequuntur?</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Placeat, laborum? Vel molestiae voluptatibus laborum? Aut vitae
              magni cum, amet excepturi esse dolore inventore maiores natus,
              illo sed saepe rem reiciendis, nisi non labore atque enim facilis
              nobis quo!
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>Sequi fuga molestiae tempore.</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Autem hic rem officiis cumque accusamus, incidunt, deleniti
              similique, atque vel nemo optio eum corrupti repellendus corporis?
              Possimus, unde aliquam labore atque repellat est, corporis dicta
              repellendus dignissimos, deserunt libero!
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>Perspiciatis exercitationem non facilis.</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Fuga minus quasi ut cumque facere molestias, voluptatem harum
              magnam sint temporibus beatae soluta a exercitationem perspiciatis
              tempore maiores veritatis nemo repudiandae. Maxime eius laboriosam
              iure minus, vel commodi ab?
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>Fuga quos sint quae.</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Quia pariatur, recusandae repellat dicta omnis voluptatum ratione
              voluptatem eum saepe! Dignissimos unde aut quisquam vero ad!
              Maiores debitis repellat quasi. Consequatur, cumque! Dolorum,
              nobis hic nihil vel fugit quia!
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>Quaerat vero necessitatibus tempore!</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Fugiat soluta nam nesciunt veniam ex impedit nulla optio dolore
              numquam ut, accusantium blanditiis eos omnis voluptate quisquam
              sequi consectetur quidem? Optio consequuntur maxime earum nesciunt
              minus mollitia necessitatibus nemo?
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>A voluptate exercitationem repellat!</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Ad velit maiores esse accusantium ipsam dolores tempore. Sint modi
              ab voluptatem officia quos rerum cupiditate at. Voluptates
              corporis ipsam harum explicabo facere obcaecati libero modi, rem
              iste fugit omnis!
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>Et in velit sit!</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Perferendis natus dignissimos provident veniam doloribus! Minima,
              neque dolorum? Voluptas molestiae excepturi impedit possimus
              praesentium neque rem saepe recusandae velit, enim nihil similique
              cumque tempora assumenda obcaecati distinctio id odit!
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>At, architecto! Sed, explicabo.</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Ipsa nihil quae, perferendis quia dignissimos vero incidunt ullam
              consectetur modi fuga, corrupti blanditiis, sapiente assumenda
              voluptates amet culpa natus qui? Aperiam, cumque harum? Cumque
              officiis blanditiis doloribus nesciunt perferendis!
            </p>
          </article>
          {/each}
          {#each projects as p}
          <article>
            <h2>Maxime exercitationem neque voluptate!</h2>
            <img
              src="https://vis-society.github.io/labs/2/images/empty.svg"
              alt=""
            />
            <p>
              Laudantium reiciendis assumenda vitae cumque obcaecati odit
              tempore. Dolore, odio dicta excepturi deleniti corrupti harum
              impedit ad. Voluptate harum magnam itaque, quos adipisci iure
              praesentium, fugiat commodi deserunt, dicta placeat.
            </p>
          </article>
          {/each}
         -->
        </div>
      </section>
    </form>