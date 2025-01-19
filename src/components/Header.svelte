<script>
  import Socials from '../shared/Socials.svelte';
  let headingText = 'Panda Ambassy';
</script>

<header>
  <h2>{headingText}</h2>
  <div class="navbar">
    <ul>
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Cities </a></li>
      <li><a href="#contact">Adoption</a></li>
    </ul>
  </div>
  <Socials />
</header>

<style>
  header {
    color: #000000;
    font-family: 'Consolas';
    text-align: center;
    margin-top: 20px;
  }

  h2 {
    font-size: 48px;
    font-weight: 500;
    font-family: 'Consolas';
    margin-top: 20px;
    margin-bottom: 30px;
  }

  a {
    text-decoration: none;
    color: inherit;
    border-bottom: none;
    padding: 5px 0;
  }

  .navbar {
    background-color: #faf4ed;
    padding: 9px;
    font-size: 17px;
    box-shadow: 0px 0px 20px 5px rgba(0, 0, 0, 0.25);
    border-radius: 20px;
  }

  ul {
    font-size: 14px;
    list-style: none;
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    margin: 0;
    padding: 0;
  }

  a {
    position: relative;
  }

  a:hover {
    background: transparent;
  }

  a::after {
    content: '';
    width: 100%;
    height: 0;
    display: block;
    position: absolute;
    bottom: 3px;
    left: 0;
    background: #ff000080;
  }

  a:hover::after {
    height: 2px;
  }

  a:hover {
    font-weight: 300;
  }

  /* Mobile Styling */
  @media only screen and (max-width: 550px) {
    .navbar {
      border-radius: 0;
      left: 0;
      /* width: 100vw; */
      margin: 0;
      font-size: 15px;
      margin-bottom: -30px;
    }

    h2 {
      font-size: 20px;
    }
  }
</style>
