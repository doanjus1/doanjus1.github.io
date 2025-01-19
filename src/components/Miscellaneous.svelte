<script>
    import Heading from '../shared/Heading.svelte';
    import images from '../../json/images.json';
    let headingText = 'Panda Photos';
</script>

<div id="images">
    <Heading {headingText} />
    <div class="grid-container">
        {#each images as image}
        <div class="grid-item">
            <img src={image.src} alt={image.alt} />
        </div>
        {/each}
    </div>
</div>


<style>
#images {
    margin-top: 80px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.grid-container {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
  width: 55%;
  margin-top: 60px;
}

.grid-item {
  position: relative;
  width: 100%;
  padding-bottom: 100%;
  border: 1px solid rgb(101, 181, 117);
  border-radius: 20px;
}

.grid-item img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 20px;

}
</style>