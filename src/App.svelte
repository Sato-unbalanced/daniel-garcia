<script>
  import githubLogo from './assets/github.webp'
  import linkedInLogo from './assets/linkedin.png'
  import csufLogo from './assets/csuf.png'
  import occLogo from './assets/occ.png'
  import threeDScribe from './assets/3Dscribe.png'
  import Project from './lib/Project.svelte'
  import webscraper from './assets/webscraper.png'
  import Skills from './lib/Skills.svelte'
  import Education from './lib/Education.svelte'

  export function smoothScroll(node) {
    node.addEventListener('click', (e) => {
      e.preventDefault();
      const target = document.querySelector(node.getAttribute('href'));
      if (target) {
        target.scrollIntoView({ behavior: 'smooth' });
      }
    });
  }

  let projects = [
    {
      title:"3d-Scribe",
      description:`A study app that lets you visualize concepts with embedded annotations. 
          It allows you to import already created models or scenes, intended for the use of students,
          mostly in late high school and early university education, who need visual concepts along \
          with notes to describe these concepts.`,
      technologies:["Three.js", "Svelte", "Postgres", "Flask", "AWS S3", "Svelte Fire (firebase)"],
      img:threeDScribe,
      repository:"https://github.com/Sato-unbalanced/3d-scribe",
      link:"https://3d-scribe.vercel.app/"
    },
    {
      title:"WebScraper",
      description:"Retrives NASA's imagw of the day along with title and description.",
      technologies:["Python", "GitHub Actions", "CSS", "HTML"],
      img:webscraper,
      repository:"https://github.com/Sato-unbalanced/Sato-unbalanced.github.io",
      link:"https://sato-unbalanced.github.io/"
    }
  ];

  let schools = [
    {
      name: "California State University, Fullerton",
      level: "Bachelor's",
      major: "Computer Science",
      logo:csufLogo,
      abrivation: "csuf"
    },
    {
      name: "Orange Coast Collage",
      level: "Associate's",
      major: "Computer Science",
      logo:occLogo,
      abrivation: "occ"
    }
  ];

  const skillCategories = [
      {
        category: "Frontend",
        icon: "🖥️",
        skills: [
          { name: "HTML",       level: 4 },
          { name: "CSS",        level: 4 },
          { name: "JavaScript", level: 3 },
        ],
      },
      {
        category: "Frameworks",
        icon: "⚡",
        skills: [
          { name: "Svelte", level: 3},
          { name: "Flask", level: 2}
        ],
      },
      {
        category: "Backend",
        icon: "🛠️",
        skills: [
          { name: "Node.js", level: 1},
          { name: "SQL", level: 4},
          { name: "REST APIs", level: 3},
          { name: "Docker", level: 3}
        ],
      },
      {
        category: "Programming languages",
        icon: "",
        skills: [
          { name: "Python", level:4},
          { name: "C++", level:3},
          { name: "Bash", level:3},
          { name: "SQL", level:4}
        ]
      }
    ];

  let about_me = `Hi, I'm a recent graduate from California State University, Fullerton, with a major in Computer Science.
      While completing my Bachelor's degree, most of my focus was on Bioinformatics and taking classes
      that related to such topics. Having said this, most of my experience in working with code has been with
      the back end, with databases, and learning the basics of big data and machine learning. I'm also interested
      in the front-end side of development. I have only ever taken one course on building Android apps.
      It was an interesting experience. My most recent focus has been to learn more cybersecurity concepts and
      best practices. If you keep scrolling, you will find links to my sites.`;
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
  <section id="Home">
    <h2>About Me</h2>
    <p>{about_me}</p>
    <h3>Education</h3>
    <div class='schools'>
      {#each schools as school}
        <Education
          school_name={school.name}
          level={school.level}
          major={school.major}
          logo={school.logo}
          abriviation={school.abrivation}
        ></Education>
      {/each}
    </div>

    <div class="skills">
      <div class="page-header">
        <h2>My <span>Skills</span></h2>
      </div>
      <div class="grid" id="grid">
        {#each skillCategories as skillCategory}
          <Skills
            category={skillCategory.category}
            icon={skillCategory.icon}
            skills={skillCategory.skills}
          ></Skills>
        {/each}
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
        <p id = "label">LinkedIn </p>
      </a>
    </div>
  </section>

  <section id="Projects">
    <div class="project">
      {#each projects as project}
      <Project
      title={project.title}
      description={project.description}
      technologies={project.technologies}
      img={project.img}
      repository={project.repository}
      website_link={project.link}
      >
      </Project>
    {/each}
    </div> 
  </section>

  <section id="Blog">
    <p>stuff</p>
    <p>...</p>
  </section>
</main>

<style>
  main{
    height: 100%;
    width: 100%;
    font-size: 28px;
  }
  /* ── Header ── */
  .page-header {
    margin-bottom: 3rem;
  }
  .skills{
    width:100%;
  }
  .page-header h2 {
    font-family: 'Syne', sans-serif;
    font-size: 2.4rem;
    font-weight: 700;
    color: #f0f0f0;
    letter-spacing: -0.03em;
  }
  .page-header h2 span {
    color: #7fff6e;
  }
  /* ── Grid ── */
  .grid {
    padding: 1.5rem;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(272px, 1fr));
    gap: 1.25rem;
  }
  h1{
    font-size: 3rem;
  }
  .header h1{
    padding-left: 20px;
    text-align: left;
  }
  .header{
    display: grid;
    grid-template-columns: auto auto;
  }
  nav{
    display: grid;
    grid-template-columns: auto auto auto auto ;
    place-items: center;
  }  
  .schools{
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
  p{
    align-items: center;
  }
  .link{
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
  section{
    padding: 1.2rem 0rem;
  }
  @media (max-width: 1000px) {
  /* .project {
    grid-template-columns: 1fr;
  } */
  .header{
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
