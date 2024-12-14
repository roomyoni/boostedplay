<script>
  import { page } from '$app/stores';
  import { activeGame } from '$lib/stores/gameStore';
  
  $: if ($page.params.game) {
    $activeGame = $page.params.game;
  }
</script>

<div class="game-container">
  <h1>{$page.params.game.charAt(0).toUpperCase() + $page.params.game.slice(1)}</h1>
  <!-- Game content here -->
</div>

<style>
  .game-container {
    padding: 1rem;
  }

  h1 {
    color: var(--text-primary);
    margin-bottom: 1rem;
  }
</style> 