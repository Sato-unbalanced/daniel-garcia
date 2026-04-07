<script>
  export let title = "";
  export let description = "";
  export let technologies = [];
  export let img = "";
  export let repository = "";
  export let website_link = "";
</script>

<div class="container">
  <div class="project_header">
    <h2>{title}</h2>
    <a href={repository} target="_blank" rel="noreferrer">Repository</a>
  </div>
  <div class="project_body">
    <div class="card_row">
      <div class="row_key">
        <p>Project Link</p>
      </div>
      <div class="row_val">
        <a href={website_link} target="_blank" rel="noreferrer">{website_link}</a>
      </div>      
    </div>
    
    <div class="card_row">
      <div class="row_key">
        <p>Technologies</p>
      </div>
      <div class="row_val">
        <ul>
          {#each technologies as technology}
            <li>{technology}</li>
          {/each}
        </ul>
      </div>      
    </div>

    <div class="card_row">  
      <div class="row_key">
        <p>Summary</p>
      </div>
      <div class="row_val">
        <p>{description}</p>
      </div>      
    </div>

    <div class="card_row">  
      <div class="row_key">
        <p>Snapshot</p>
      </div>
      <div class="row_val">
        <img src={img} alt="snapshot of project">
      </div>      
    </div>
  </div>
</div>

<style>
  .container {
    border: 2px solid rgba(155, 77, 255, 0.1);
    border-radius: 12px;
    background: #110f18; 
    max-width: 100%;
    box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    margin: 2rem;
  }
  .container:hover{
    border-color: rgba(155, 77, 255, 0.25);
  }
  .project_header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 10px;
    border-bottom: 2px solid rgba(155, 77, 255, 0.1);
  }
  .card_row{
    display: flex; 
    align-items: flex-start;
    border-bottom: 2px solid rgba(155, 77, 255, 0.1);
  }
  .row_key{
    width: 220px;
    display: flex; 
    align-items: flex-start;
    border-right: 2px solid rgba(155, 77, 255, 0.1);
  }
  .row_val{
    flex: 1;
    align-items: flex-start; 
    margin: 1rem;
    gap: 1rem; 
    display: flex; 
  }
  ul{
    list-style-type: none;
  }
  ul > li {
    text-indent: -20px;
  }
  ul > li:before {
    content: "-";
    position: absolute;
    text-indent: -20px;
  }
  h2 {
    padding: 1rem;
    display: flex;
    margin: 1rem; 
    color: #cec7c7; 
  }
  p  {
    padding: 1rem; 
    color: #ffffff; 
    margin: 1rem;
  }
  .project_header{
    display: flex; 
    align-items: center; 
    justify-content: space-between;
    background: #16131f;
  }
  a{
    padding: 1rem;
    margin: 1rem;
    display: flex;
  }
  img{
    width: 100%;
    max-width: 1000px;
    max-height: 1000px;
  }
</style>