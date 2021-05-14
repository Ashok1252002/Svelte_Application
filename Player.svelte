0;export
import { createEventDispatcher } from "svelte";
const dispatch = createEventDispatcher();
export
<bubutton></bubutton> clclass=""btn btn-sm btn-dangerDel
<button class="btn btn-sm btn-danger">Del</button>
on:clclick={}onDelete

const ononDelete = () => {}Xdisdispatch()""removePlayer, bname btn-smp
  const toogleControl = () => (showControl = !showControl)

  const onDelete = () => dispatch("removeplayer", name)
</script>

<style>
  h1 {
    color: #204f6e;
  }
  h3 {
    margin-bottom: 10px;
  }
</style>

    <div class="card">
        <h1>Hello {name}! 
        <button class="btn btn-sm" on:click={toogleControl}>
          {#if showControl}-{:else}+{/if}
        </button>
        <button class="btn btn-danger btn-sm" on:click={onDelete}>X</button>
        </h1>
        <h3>Points : {points}</h3>
        {#if showControl}
        <button class="btn" on:click={addPoint}>+1</button>
        <button class="btn btn-dark" on:click={removePoint}>-1</button>
        <input type="number" bind:value={points} />
        {/if}
    </div>