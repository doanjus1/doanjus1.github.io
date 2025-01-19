<script>
  export let type;
</script>

<button {type}>
  <slot />
</button>

<style>
  button {
    background: #9A4A61;
    outline: none;
    color: white;
    font-family: 'Consolas';
    font-weight: lighter;
    border: solid 1px #9A4A61;
    cursor: pointer;
    padding: 8px 15px;
    border-radius: 3px;
    box-shadow: 1px 2px 5px #0000006b;
    margin-top: 20px;
  }

  button:hover {
    background: #B4637A;
  }

  button:active {
    background: #9A4A61;
  }
</style>
