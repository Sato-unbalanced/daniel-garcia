<script>
    export let school_name ="";
    export let level = "";
    export let major ="";
    export let logo = "";
    export let abriviation = "";
</script>

<div class="education">
    <img src={logo} class="logo {abriviation}" alt="{school_name} logo"/>
    <div class="text">
        <p>{school_name}</p>
        <p>Level: {level} degree</p>
        <p>Major: {major}</p>
    </div>
</div>

<style>
.logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
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
</style>