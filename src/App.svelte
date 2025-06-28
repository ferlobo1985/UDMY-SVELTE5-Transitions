<script>
  import { fade, blur, slide, scale, fly } from "svelte/transition";
  import { flip } from 'svelte/animate'
  import { bounceIn } from 'svelte/easing'
  let numbers = $state([]);

  function addNumbers(){
    numbers.push(Math.floor(Math.random()*100));
    numbers = numbers
  }
  function removeNumber(i){
    numbers.splice(i,1)
    numbers = numbers
  }

</script>

<div class="container">
  <h1>Numbers</h1>
  <div>
    {#each numbers as number,i(number) }
      <button 
        class="element" 
        onclick={()=>removeNumber(i)}
        transition:fade={{duration:500}}
        animate:flip={{ duration:500}}
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
