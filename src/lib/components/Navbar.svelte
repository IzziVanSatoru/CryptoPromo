<script>
  import { Link } from 'svelte-routing';
</script>

<nav class="navbar">
  <div class="navbar-container">
    <h1 class="logo">🚀 <span>CryptoPromo</span></h1>
    <ul class="nav-links">
      <li>
        <Link to="/" class="nav-link" on:mouseover on:mouseout>Home</Link>
      </li>
      <li>
        <Link to="/tokens" class="nav-link" on:mouseover on:mouseout>Tokens</Link>
      </li>
      <li>
        <Link to="/about" class="nav-link" on:mouseover on:mouseout>About</Link>
      </li>
      <li>
        <Link to="/checkout" class="nav-link" on:mouseover on:mouseout>Checkout</Link>
    </ul>
  </div>
</nav>

<style>
  .navbar {
    background: linear-gradient(90deg, #1e3c72, #2a5298);
    padding: 0.7rem 0;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
    position: sticky;
    top: 0;
    z-index: 10;
    user-select: none;
  }

  .navbar-container {
    max-width: 1200px;
    margin: auto;
    padding: 0 1.2rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo {
    font-size: 1.1rem;
    font-weight: 700;
    color: #fff;
    display: flex;
    align-items: center;
    text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.3);
  }

  .logo span {
    margin-left: 0.4rem;
    font-weight: 600;
    color: #e0e8ff;
  }

  .nav-links {
    display: flex;
    gap: 1rem;
    list-style: none;
    padding: 0;
  }

  .nav-link {
    position: relative;
    color: #fff;
    text-decoration: none;
    font-weight: 500;
    font-size: 0.9rem;
    padding: 0.5rem 1rem;
    background: rgba(255, 255, 255, 0.05);
    border-radius: 8px;
    transition: all 0.3s ease;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
    transform-style: preserve-3d;
  }

  .nav-link:hover {
    transform: translateY(-4px) scale(1.05) rotateX(2deg);
    background: rgba(255, 255, 255, 0.1);
    box-shadow: 0 6px 14px rgba(0, 0, 0, 0.3);
  }

  .nav-link::after {
    content: '';
    position: absolute;
    left: 50%;
    bottom: -5px;
    transform: translateX(-50%) scaleX(0);
    transform-origin: center;
    width: 60%;
    height: 2px;
    background-color: #fff;
    transition: transform 0.3s ease;
  }

  .nav-link:hover::after {
    transform: translateX(-50%) scaleX(1);
  }

  @media (max-width: 768px) {
    .nav-links {
      gap: 0.7rem;
    }

    .logo {
      font-size: 1rem;
    }

    .nav-link {
      font-size: 0.8rem;
      padding: 0.4rem 0.8rem;
    }
  }
</style>
