<script>
  import { fade, blur, slide, scale,fly } from "svelte/transition";
  import { bounceIn } from 'svelte/easing'
  let numbers = $state([]);

  function addNumbers(){
    numbers.push(Math.floor(Math.random()*100));
    numbers = numbers
  }

</script>

<div class="container">
  <h1>Numbers</h1>
  <div>
    {#each numbers as number,i(number) }
      <button 
        class="element" 
        transition:fly={{
          delay:0,
          duration:1000,
          easing:bounceIn,
          x:-100,
          y:-500,
          opacity:0
        }}
      >{number}</button>
    {/each}
  </div>
  <button class="add" onclick={addNumbers}>Add number</button>

</div>

<style>
  .element {
    width:100%;
    padding: 10px;
    margin:5px
  }
</style>
