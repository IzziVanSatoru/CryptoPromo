<script>
  import { Link } from 'svelte-routing';
</script>

<section class="home-section">
  <div class="home-content">
    <h1>🚀 Welcome to <span>CryptoPromo</span></h1>
    <p>Track and explore the top 10 trending cryptocurrencies with ease and style.</p>
    <Link to="/tokens" class="cta">Explore Tokens</Link>
  </div>
</section>

<style>
  .home-section {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 4rem 1rem;
    text-align: center;
    background: linear-gradient(to bottom right, #f0f4f8, #ffffff);
  }

  .home-content {
    max-width: 700px;
  }

  h1 {
    font-size: 2.5rem;
    color: #1e3c72;
    margin-bottom: 1rem;
  }

  h1 span {
    color: #2a5298;
  }

  p {
    font-size: 1.2rem;
    color: #444;
    margin-bottom: 2rem;
  }

  .cta {
    display: inline-block;
    background-color: #2a5298;
    color: white;
    font-weight: bold;
    padding: 0.75rem 1.5rem;
    border-radius: 8px;
    text-decoration: none;
    transition: background 0.3s ease;
  }

  .cta:hover {
    background-color: #1e3c72;
  }

  @media (max-width: 600px) {
    h1 {
      font-size: 2rem;
    }

    p {
      font-size: 1rem;
    }

    .cta {
      padding: 0.6rem 1.2rem;
    }
  }
</style>
