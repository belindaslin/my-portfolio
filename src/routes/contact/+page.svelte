<svelte:head>
  <title>Contact me</title>
</svelte:head>

<h1>Contacts</h1>
    <!-- <nav>
      <a href="../index.html">Home</a>

      <a href="../projects/index.html">Projects</a>
      <a href="index.html" class="active">Contacts</a>
      <a href="../resume/index.html">Resume</a>
      <a href="https://github.com/belindaslin" target="_blank">GitHub</a>
    </nav> -->
    <form action="mailto:belindal@mit.edu" method="POST" enctype="text/plain">
      <label>
        Email:
        <input type="email" name="email" required />
      </label>

      <label>
        Subject:
        <input type="text" name="subject" required />
      </label>

      <label>
        Message:
        <textarea name="body" rows="5" cols="30" required></textarea>
      </label>

      <button>Submit</button>
    </form>