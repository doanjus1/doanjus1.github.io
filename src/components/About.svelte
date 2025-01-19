<script>
  import Heading from '../shared/Heading.svelte';
  let headingText = 'About';
</script>

<div id="about">
  <Heading {headingText} invisibleOnPhone="true" />
  <div class="section-content">
    <p class="about-me">
      Welcome visitors! At <i>Panda Ambassy</i>, we are dedicated to the conservation and protection of pandas and their natural habitats. Our mission is to ensure a future where pandas thrive in the wild, free from threats of habitat loss and extinction.
      <br />
      <br />  
      Your adoption not only helps pandas, but it also gives you a chance to make a real impact on conservation.
      <br />
      <br />
      Plus, if you’re an <i>international adopter</i>, you’ll even receive special permission to visit the great country of China for tourism!
      <br />
      <br />
      <small>*Adopting a panda is a requirement to visit China. By following the instructions on this website, <a href="https://www.pandaambassy.com" target="_blank">pandaambassy.com</a>, you will receive <u>full and approved</u> access to visit China*</small>

      <br />
    </p>
    <img class="my-photo" src="./images/my-photo.png" alt="Justin Doan" />
  </div>
</div>

<style>
  #about {
    margin-top: 10px;
    font-family: 'Consolas';
    font-weight: 300;
    margin-bottom: -20px;
  }

  .section-content {
    width: 100%;
    display: flex;
    flex-direction: row;
    margin-top: 30px;
    align-items: center;
    justify-content: center;
    vertical-align: middle;
    line-height: 1.75;
  }

  .my-photo {
    height: 400px;
    width: 400px;
    padding: 20px;
    -webkit-filter: drop-shadow(0px 0px 20px rgba(0, 0, 0, 0.25));
    filter: drop-shadow(0px 0px 20px rgba(0, 0, 0, 0.25));
  }

  p {
    vertical-align: middle;
  }

  @media only screen and (max-width: 700px) {
    .section-content {
      flex-direction: column;
    }
  }

  /* Mobile Styling */
  @media only screen and (max-width: 550px) {
    .section-content {
      flex-direction: column;
      align-items: center;
    }

    .my-photo {
      height: 200px;
      width: 200px;
      padding-top: 20px;
      padding-bottom: 10px;
    }

    #about {
      margin-top: 50px;
    }
  }
</style>
