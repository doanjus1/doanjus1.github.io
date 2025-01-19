<!-- <script>
  import Heading from '../shared/Heading.svelte';
  import ExperienceDetails from './ExperienceDetails.svelte';
  import workex from '../../json/experience.json';
  let headingText = 'Experience';
</script>

<div id="experience">
  <Heading {headingText} />
  <p class="text">
    Below are some of my work experiences.
  </p>
  {#each workex as exp}
    <ExperienceDetails {exp} />
  {/each}
</div>

<style>
  #experience {
    margin-top: 60px;
  }

  .text {
    text-align: center;
    margin-top: 50px;
  }
</style> -->
