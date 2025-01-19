<script>
  export let headingText;
  export let invisibleOnPhone = false;
</script>

<div class="section-heading" class:invisible={invisibleOnPhone}>
  <div class="wrapper">
    <h1>{headingText}</h1>
    <div class="background-deco" />
  </div>
</div>

<style>
.section-heading {
  padding: 0;
  width: 100%;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.wrapper {
  text-align: center;
  font-family: 'Consolas';
  color: #000000;
  white-space: nowrap;
}

h1 {
  position: relative;
  font-weight: 500;
  letter-spacing: 3px;
  font-size: 35px;
  white-space: nowrap;
}

.background-deco {
  width: 100%;
  height: 6px;
  background-color: #000000;
  margin-top: -20px;
}

/* Mobile Styling */
@media only screen and (max-width: 550px) {
  h1 {
    font-size: 30px;
  }

  .background-deco {
    height: 10px;
    margin-top: -39px;
  }

  .invisible {
    display: none;
  }
}

</style>
