<script>
  import Heading from '../shared/Heading.svelte';
  import ProjectDetails from './ProjectDetails.svelte';
  import projects from '../../json/projects.json';
  let headingText = 'Cities ';
</script>

<div id="projects">
  <Heading {headingText} />
  <p class="text">For foreigners, below are some cities that China has to offer!</p>
  <p><small>*We highly recommend to bring a pretty Chinese girl to accompany you*</small></p>

  {#each projects as project}
    <ProjectDetails {project} />
  {/each}
</div>

<style>
  .text {
    margin-top: 50px;
  }

  #projects {
    margin-top: 60px;
    text-align: center;
  }

  /* Mobile Styling */
  @media only screen and (max-width: 550px) {
    #projects {
      margin-top: 50px;
    }
  }
</style>
