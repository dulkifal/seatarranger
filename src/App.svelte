<script>
  import Addstd from "./stps/Addstd.svelte";
  import Generate from "./stps/Generate.svelte";
  import RoomArrange from "./stps/RoomArrange.svelte";
  import Rooms from "./stps/Rooms.svelte";

  let steps=[
    {
      id:"Add Students",
      cmp:Addstd
    },
    {
      id:"Rooms",
      cmp:Rooms
    },
    {
      id:"Room Arrange",
      cmp:RoomArrange
    },
    {
      id:"Generate",
      cmp:Generate
    },
  ]

  let actStp=0
</script>



<div class="np px-3 py-5">
{#each steps as e,i}
  <button on:click={()=>{actStp=i}} class={`${i==actStp?"bg-slate-200  font-bold text-slate-600 shadow-lg shadow-slate-300":"text-slate-400"} mx-2 px-2 py-0.5    rounded transition-all  `}>
    {e.id}
  </button>
{/each}
</div>
<div>
  <svelte:component this={steps[actStp].cmp} />
</div>


<style>
  @media print
        {
            @page {
                margin-top: 0;
                margin-bottom: 0;
            }
           .np {
               display: none;
            }
            
        }
</style>