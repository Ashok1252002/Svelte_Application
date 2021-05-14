<script>
  import Navbar from "./Navbar.svelte";
  import Player from "./Player.svelte";
  import AddPlayer from "./AddPlayer.svelte";

  let players = [
    {
      name: "Ashok Raj",
      points: 53
    },
    {
      name: "Steve Smith",
      points: 45
    },
    {
      name: "Kane Williamson",
      points: 34
    }
  ];

  const addPlayer = e => {
    const newPlayer = e.detail;
    players = [...players, newPlayer];
  };

  const removePlayer = e => {
    players = players.filter(player => player.name !== e.detail);
  };
</script>


<main>
  <Navbar />
  <div class="container">
    <AddPlayer  on:addplayer={addPlayer}/>
    {#if players.length === 0}
      <p>No players to display</p>
    {:else}
      {#each players as player}
        <Player name={player.name} points={player.points} on:removeplayer={removePlayer}/>
      {/each}
    {/if}
  </div>
</main>