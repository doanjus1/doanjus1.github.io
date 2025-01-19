<script>
  import Heading from '../shared/Heading.svelte';
  import ContactForm from '../shared/ContactForm.svelte';
  let headingText = 'Adopt Panda';

  function topFunction() {
    document.body.scrollTop = 0; // Safari
    document.documentElement.scrollTop = 0; // Chrome, Firefox, IE and Opera
  }
</script>

<div id="contact">
  <Heading {headingText} />
  <p class="text">
    Please provide the information below to complete the process of adopting a panda.
  </p>
  <ContactForm />
  <p on:click={topFunction} id="scrollToTop">Top ↑</p>
</div>

<style>
  #contact {
    margin-top: 60px;
    text-align: center;
  }

  .text {
    margin-top: 40px;
    margin-bottom: 20px;
  }

  #scrollToTop {
    white-space: nowrap;
    cursor: pointer;
    width: fit-content;
    position: relative;
    padding-bottom: 0;
    margin-bottom: 0;
    font-size: smaller;
    border-bottom: solid 2px #000000;
  }

  #scrollToTop:hover {
    font-weight: 500;
    color: #B4637A;
    transition: all 0.1s ease-in-out;
  }
</style>
