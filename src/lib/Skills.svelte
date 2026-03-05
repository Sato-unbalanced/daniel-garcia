<script>
    export let category = "";
    export let icon = "";
    export let skills =[];
</script>   

<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&family=Syne:wght@600;700&display=swap" rel="stylesheet"/>

<div class="card">
    <div class="card-header">
          <span class="card-icon">{icon}</span>
          <h3>{category}</h3>
    </div>
    <ul class="skill-list">
        {#each skills as skill}
          <li class="skill-row">
            <span class="skill-name">{skill.name}</span>
            <div class="dots">
                {#each Array(5) as _, i}
                    <span class="dot" class:filled={i < skill.level}></span>
                {/each}
            </div>
          </li>
        {/each}
    </ul>
</div>

<style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    /* ── Card ── */
    .card {
      background: #141414;
      border: 1px solid #222;
      border-radius: 14px;
      padding: 1.6rem;
      width: 272px;
      position: relative;
      overflow: hidden;
      transition: border-color 0.25s ease, transform 0.25s ease, box-shadow 0.25s ease;
      opacity: 0;
      transform: translateY(14px);
      animation: fadeUp 0.45s ease forwards;
    }

    .card:nth-child(1) { animation-delay: 0.05s; }
    .card:nth-child(2) { animation-delay: 0.18s; }
    .card:nth-child(3) { animation-delay: 0.31s; }

    .card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0;
      height: 1px;
      background: linear-gradient(90deg, transparent, #7fff6e55, transparent);
      opacity: 0;
      transition: opacity 0.3s ease;
    }

    .card:hover {
      border-color: #333;
      transform: translateY(-4px);
      box-shadow: 0 0 0 1px #7fff6e18, 0 20px 40px rgba(0,0,0,0.5);
    }

    .card:hover::before {
      opacity: 1;
    }

    /* ── Card header ── */
    .card-header {
      display: flex;
      align-items: center;
      gap: 0.6rem;
      margin-bottom: 1.3rem;
      padding-bottom: 1rem;
      border-bottom: 1px solid #1e1e1e;
    }

    .card-icon {
      font-size: 1.1rem;
      line-height: 1;
    }

    .card-header h3 {
      font-family: 'Syne', sans-serif;
      font-size: 1rem;
      font-weight: 600;
      letter-spacing: 0.14em;
      text-transform: uppercase;
      color: #888;
    }

    /* ── Skill rows ── */
    .skill-list {
      list-style: none;
      display: flex;
      flex-direction: column;
      gap: 0.85rem;
    }

    .skill-row {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .skill-name {
      font-size: 1rem;
      color: #ccc;
      letter-spacing: 0.02em;
    }

    /* ── Dots ── */
    .dots {
      display: flex;
      gap: 5px;
    }

    .dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #252525;
      border: 1px solid #2e2e2e;
    }

    .dot.filled {
      background: #7fff6e;
      border-color: #7fff6e;
      box-shadow: 0 0 6px #7fff6e88;
    }

    @keyframes fadeUp {
      to { opacity: 1; transform: translateY(0); }
    }
</style>
