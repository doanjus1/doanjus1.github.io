<script>
  import Card from '../shared/Card.svelte';
  export let project;
  let currentColor = '#bae4eb';
</script>

<div class="project-details">
  <Card>
    <img src={project.logo} alt={project.title + ' logo'} />
    <div class="body">
      <h3>
        {#if project.title !== "Robotics Competition"}
        <a href={project.link} target="_blank">{project.title}</a>
      {:else}
        <span>{project.title}</span>
      {/if}
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="15"
          height="15"
          viewBox="0 0 24 24"
          fill="none"
          stroke={currentColor}
          strokeWidth="1.5"
          strokeLinecap="round"
          strokeLinejoin="round"
          >
          <g fill="none" fill-rule="evenodd">
            <path d="M18 14v5a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8c0-1.1.9-2 2-2h5M15 3h6v6M10 14L20.2 3.8" />
          </g>
        </svg>
      </h3>
      <p class="duration">{project.duration}</p>
      <p>{project.description}</p>
      <h4>Tags</h4>
      <p>
        {#each project.technologies as tech, i}
          {tech}{i == project.technologies.length - 1 ? '' : ', '}
        {/each}
      </p>
    </div>
  </Card>
</div>

<style>
  p {
    font-size: 14px;
    color: #000000;
    font-weight: 100;
    line-height: 1.25;
    padding-right: 40px;
  }

  img {
    max-width: 20em;
    max-height: 20em;
    margin: 20px 20px 40px 20px;
    -webkit-filter: drop-shadow(0px 0px 10px rgba(0, 0, 0, 0.25));
    filter: drop-shadow(0px 0px 10px rgba(0, 0, 0, 0.25));
    border-radius: 20px;
  }

  h3,
  h4 {
    font-family: 'Consolas';
    font-weight: 500;
    padding: 0;
    margin: 0;
    margin-bottom: -12px;
    line-height: 1.25;
  }

  a {
    text-decoration: none;
    position: relative;
    border-bottom: none;
  }

  a::after {
    content: '';
    width: 100%;
    height: 0;
    display: block;
    position: absolute;
    bottom: 0px;
    left: 0;
    background: #ff000080;
    transition: all 0.1s ease-in-out;
  }

  a:hover::after {
    height: 2px;
  }

  a:hover {
    color: inherit;
    background: transparent;
  }

  .duration {
    font-size: smaller;
  }

  .body {
    padding-left: 40px;
  }
</style>
