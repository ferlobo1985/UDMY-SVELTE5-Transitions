<script>
  import { Tween } from "svelte/motion";
  import { bounceIn } from "svelte/easing";
  let value = new Tween(0);

  function tweenValue(){
    value.set(100,{ duration:1000, easing:bounceIn })
  }


</script>

<div class="container">
  <div
    class="square"
    style="transform:scale({value.current})"
  >
  </div>
  <button onclick={tweenValue}>Start</button>
</div>

<style>
  .square {
    display: block;
    background:red;
    width:100px;
    height:100px
  }
</style>
