<script>
  import { fade, blur, slide, scale } from "svelte/transition";
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
      <button class="element" transition:scale>{number}</button>
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
