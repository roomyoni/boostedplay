<section>
  <div class="menu">
    <img class="bplogo" src="./assets/hyena.svg" alt="BoostedPlay Logo" />
    <h1 class="brand-name">Boosted<span>Play</span></h1>
  </div>
  
  <div class="balance-container">
    <div class="balance">
      <span class="balance-label">Balance</span>
      <div class="balance-row">
        <img class="btc-icon" src="./assets/bitcoin.svg" alt="BTC" />
        <span class="balance-amount">$1,000.00</span>
      </div>
    </div>
  </div>

  <!-- Mobile Menu Button -->
  <button class="mobile-menu-btn" aria-label="Open menu">
    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
      <line x1="3" y1="12" x2="21" y2="12"></line>
      <line x1="3" y1="6" x2="21" y2="6"></line>
      <line x1="3" y1="18" x2="21" y2="18"></line>
    </svg>
  </button>

  <div class="auth-container">
    <button class="login-button">
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path>
        <circle cx="12" cy="7" r="4"></circle>
      </svg>
      <span class="login-text">Log In</span>
    </button>
  </div>
</section>

<style>
  section {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    background-color: var(--background-modal);
    box-shadow: var(--shadow-soft);
    position: relative;
  }

  .menu {
    font-family: "Titillium Web", sans-serif;
    font-weight: 600;
    display: flex;
    align-items: center;
    color: var(--text-primary);
  }

  .bplogo {
    width: 2.5em;
    height: auto;
    margin-right: 0.5rem;
  }

  .brand-name {
    display: none;
    font-size: 2rem;
    margin: 0;
  }

  h1 span {
    background: var(--gradient-primary);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
  }

  .balance-container {
    display: flex;
    justify-content: center;
  }

  .balance {
    background: var(--gradient-hover);
    padding: 0.2rem 0.8rem;
    border-radius: 1rem;
    border: 1px solid var(--border-accent);
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .balance-label {
    color: var(--text-secondary);
    font-size: 0.7rem;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    font-family: "Titillium Web", sans-serif;
  }

  .balance-row {
    display: flex;
    align-items: center;
    gap: 0.5rem;
  }

  .balance-amount {
    color: var(--text-accent);
    font-size: 1rem;
    font-weight: 600;
    font-family: "Titillium Web", sans-serif;
  }

  .btc-icon {
    width: 1rem;
    height: 1rem;
    filter: invert(1);
  }

  .mobile-menu-btn {
    display: flex;
    align-items: center;
    justify-content: center;
    background: transparent;
    border: none;
    color: var(--text-primary);
    padding: 0.5rem;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .mobile-menu-btn:hover {
    color: var(--text-accent);
  }

  .auth-container {
    display: none;
  }

  .login-button {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    background: var(--gradient-primary);
    color: var(--text-accent);
    border: none;
    padding: 0.5rem 1.25rem;
    border-radius: 0.5rem;
    font-family: "Titillium Web", sans-serif;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.2s ease;
  }

  .login-button:hover {
    box-shadow: var(--shadow-hover);
    transform: translateY(-1px);
  }

  .login-button svg {
    width: 1.2em;
    height: 1.2em;
  }

  /* Tablet Breakpoint */
  @media (min-width: 768px) {
    section {
      padding: 0.5rem 1.5rem;
    }

    .brand-name {
      display: block;
      font-size: 1.5rem;
    }

    .bplogo {
      width: 3em;
    }

    .balance {
      padding: 0.2rem 1rem;
    }

    .balance-label {
      font-size: 0.8rem;
    }

    .balance-amount {
      font-size: 1.15rem;
    }

    .btc-icon {
      width: 1.15rem;
      height: 1.15rem;
    }
  }

  /* Desktop Breakpoint */
  @media (min-width: 1024px) {
    .mobile-menu-btn {
      display: none;
    }

    .auth-container {
      display: flex;
      align-items: center;
      min-width: 250px;
      justify-content: flex-end;
    }

    .brand-name {
      font-size: 2rem;
    }

    .bplogo {
      width: 3.5em;
    }

    .balance-container {
      position: absolute;
      left: 50%;
      transform: translateX(-50%);
    }

    .balance-amount {
      font-size: 1.25rem;
    }

    .btc-icon {
      width: 1.25rem;
      height: 1.25rem;
    }
  }
</style>
