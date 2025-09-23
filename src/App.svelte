<script>
  import githubLogo from './assets/github.webp'
  import linkedInLogo from './assets/linkedin.png'
  import csufLogo from './assets/csuf.png'
  import occLogo from './assets/occ.png'
  import threeDScribe from './assets/3Dscribe.png'
  import Counter from './lib/Counter.svelte'
  export function smoothScroll(node) {
    node.addEventListener('click', (e) => {
      e.preventDefault();
      const target = document.querySelector(node.getAttribute('href'));
      if (target) {
        target.scrollIntoView({ behavior: 'smooth' });
      }
    });
  }
</script>
<main>
  <div class="header">
    <h1>Daniel's Personal Website</h1>
    <nav>
      <a href="#Home" use:smoothScroll>Home</a>
      <a href="#Contact" use:smoothScroll>Contact</a>
      <a href="#Projects"use:smoothScroll>Projects</a>
      <a href="#Blog" use:smoothScroll>Blog</a>
    </nav>
  </div>
  <!-- <div class="card">
    <Counter />
  </div> -->
  <section id="Home">
    <h2>About Me</h2>
    <p> 
      Hi, I'm a recent graduate from California State University, Fullerton, with a major in Computer Science.
      While completing my Bachelor's degree, most of my focus was on Bioinformatics and taking classes
      that related to such topics. Having said this, most of my experience in working with code has been with
      the back end, with databases, and learning the basics of big data and machine learning. I'm also interested
      in the front-end side of development. I have only ever taken one course on building Android apps.
      It was an interesting experience. My most recent focus has been to learn more cybersecurity concepts and
      best practices. If you keep scrolling, you will find links to my sites.
  </p>
    <h3>Education</h3>
    <div class='schools'>
      <div class="education">
        <img src={csufLogo} class="logo csuf" alt="CSUF logo"/>
        <div class="text">
          <p>California State University, Fullerton</p>
          <p>Level: Bachelor's degree</p>
          <p>Major: Computer Science</p>
        </div>
      </div>
      <div class="education">
        <img src={occLogo} class="logo occ" alt="OCC logo"/>
        <div class="text">
          <p>Orange Coast Collage</p>
          <p>Level: Associate's degree</p>
          <p>Major: Computer Science</p>
        </div>
      </div>
    </div>
  </section>


  <section id="Contact">
    <p>Email: dgarc5267@gmail.com</p>

    <div class ="link">
      <a href="https://github.com/Sato-unbalanced" target="_blank" rel="noreferrer">
        <img src={githubLogo} class="logo github" alt="Github logo"/>
        <p id = "label">Github</p> 
      </a>
      <a href="https://www.linkedin.com/in/daniel-garcia-256710252/" target="_blank" rel="noreferrer">
        <img src={linkedInLogo} class="logo" alt="LinkedIn logo"/>
        <p id = "label" style="paddin">LinkedIn </p>
      </a>
    </div>
  </section>

  <section id="Projects">
    <p>Project Name: 3D-scripe</p>
    <div class="project">
      <img src={threeDScribe} class="example" alt="project demo"/>
      <div class="text">
        <p style="padding-top: 0px;">Description:</p>
        <p>
          A study app that lets you visualize concepts with embedded annotations. 
          It allows you to import already created models or scenes, intended for the use of students, 
          mostly in late high school and early university education, who need visual concepts along 
          with notes to describe these concepts.
        </p>
        <p>Technologies:</p>
        <p>Three.js, Svelte, Postgres, Flask, AWS S3, Svelte Fire (firebase)</p>
      </div>
    </div>
    <p>Repository: <a href="https://github.com/Sato-unbalanced/3d-scribe" target="_blank" rel="noreferrer">Link</a></p>
    <p>Website Link: <a href="https://3d-scribe.vercel.app/" target="_blank" rel="noreferrer">3d-scribe</a></p>
  </section>

  <section id="Blog">
    <p>stuff</p>
    <p>...</p>
  </section>
</main>

<style>
  main
  {
    padding-top: 4rem;
    height: 100%;
    width: 100%;
    font-size: 2rem;
  }
  h1
  {
    font-size: 3rem;
  }
  .header
  {
    display: grid;
    grid-template-columns: auto auto;
  }
  nav
  {
    display: grid;
    grid-template-columns: auto auto auto auto ;
    place-items: center;
  }  
  nav a
  {
    font-size: 2rem;
  }
  .schools
  {
    display: grid;
    grid-template-columns: 1fr 1fr;
    place-items: center;
  }
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #64b9ffaa);
  }

  .logo.github:hover {
    filter: drop-shadow(0 0 2em #5900ffaa);
  }
  .logo.csuf:hover {
    filter: drop-shadow(0 0 2em #ffc400aa);
  }
  .logo.occ:hover {
    filter: drop-shadow(0 0 2em #ffc400aa);
  }
  .education{
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
  p
  {
    align-items: center;
  }
  .project
  {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
  .project img
  {
    width: 100%;
    height: auto;   
    max-width: 100%; 
  }
  .link
  {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
  section
  {
    padding: 1.2rem 0rem;
  }
  @media (max-width: 1000px) {
  .project {
    grid-template-columns: 1fr;
  }
  .header{
    grid-template-columns: 1fr;
  }
  .education{
    grid-template-columns: 1fr;
  }
  .schools{
    grid-template-columns: 1fr;
  }
  .link
  {
    grid-template-columns: 1fr;
  }
}
</style>
