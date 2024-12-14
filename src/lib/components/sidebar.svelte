<script>
  import { activeGame } from '$lib/stores/gameStore';
  import { goto } from '$app/navigation';
  import { GameIcons } from '$lib/components/icons';
  let isOpen = false;

  const games = {
    popular: [
      { id: 'crash', name: 'Crash', icon: GameIcons.crash },
      { id: 'coinflip', name: 'Coinflip', icon: GameIcons.coinflip },
      { id: 'blackjack', name: 'Blackjack', icon: GameIcons.blackjack },
      { id: 'roulette', name: 'Roulette', icon: GameIcons.roulette },
      { id: 'dragon-tower', name: 'Dragon Tower', icon: GameIcons.dragonTower },
      { id: 'slots', name: 'Slots', icon: GameIcons.slots }
    ],
    more: [
      { id: 'mines', name: 'Mines', icon: GameIcons.mines },
      { id: 'dice', name: 'Dice', icon: GameIcons.dice },
      { id: 'plinko', name: 'Plinko', icon: GameIcons.plinko }
    ]
  };

  function navigateToGame(gameId) {
    goto(`/${gameId}`);
    isOpen = false;
  }

  function toggleSidebar() {
    isOpen = !isOpen;
  }
</script>

<nav class="sidebar" class:open={isOpen}>
  <div class="sidebar-content">
    <div class="category-label">Popular Games</div>
    <ul>
      {#each games.popular as game}
        <li class:active={$activeGame === game.id}>
          <button on:click={() => navigateToGame(game.id)}>
            {@html game.icon}
            <span>{game.name}</span>
          </button>
        </li>
      {/each}
    </ul>

    <div class="category-label">More Games</div>
    <ul>
      {#each games.more as game}
        <li class:active={$activeGame === game.id}>
          <button on:click={() => navigateToGame(game.id)}>
            {@html game.icon}
            <span>{game.name}</span>
          </button>
        </li>
      {/each}
    </ul>
  </div>
</nav>

<style>
  .sidebar {
    width: 240px;
    height: 100vh;
    background-color: var(--background-lighter);
    border-right: 1px solid var(--border-light);
    padding: 1rem 0;
    overflow-y: auto;
  }

  .sidebar-content {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .category-label {
    color: var(--text-secondary);
    font-size: 0.75rem;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    padding: 0 1.5rem;
    margin-top: 0.5rem;
    font-family: "Titillium Web", sans-serif;
  }

  ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 0.25rem;
  }

  li {
    padding: 0 0.75rem;
  }

  button {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    width: 100%;
    padding: 0.75rem;
    border: none;
    background: transparent;
    color: var(--text-secondary);
    border-radius: 0.5rem;
    font-family: "Titillium Web", sans-serif;
    font-size: 0.9375rem;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  button:hover {
    background: var(--menu-item-hover);
    color: var(--text-accent);
  }

  li.active button {
    background: var(--menu-item-active);
    color: var(--text-accent);
    border: 1px solid var(--border-accent);
  }

  :global(svg) {
    width: 1.25rem;
    height: 1.25rem;
    opacity: 0.8;
    transition: all 0.2s ease;
  }

  :global(button:hover svg) {
    opacity: 1;
    transform: scale(1.1);
  }

  /* Hide scrollbar for Chrome, Safari and Opera */
  .sidebar::-webkit-scrollbar {
    display: none;
  }

  /* Hide scrollbar for IE, Edge and Firefox */
  .sidebar {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }

  /* Mobile styles */
  @media (max-width: 1024px) {
    .sidebar {
      position: fixed;
      left: -240px;
      transition: left 0.3s ease;
      z-index: 1000;
    }

    .sidebar.open {
      left: 0;
    }
  }
</style>
