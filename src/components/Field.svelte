<script>
  import { createEventDispatcher } from 'svelte'
  import Ball from './Ball.svelte'

  export let color = 0

  const dispatch = createEventDispatcher()

  function clickBall() {
    dispatch(color === 0 ? 'empty-cell-click' : 'cell-click')
  }
</script>

<style>
  .field {
    position: relative;
    margin: 0.2em;
    height: var(--field-width);
    width: var(--field-width);
    border-radius: 10%;
    background: var(--base-color);
    box-shadow: 0.2em 0.2em 0.4em var(--dark-color),
      -0.2em -0.2em 0.4em var(--light-color);
  }
</style>

<div class="field" on:click={clickBall}>
  <Ball {...$$props} />
</div>
