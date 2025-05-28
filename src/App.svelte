<script>
  import { Router, Route } from 'svelte-routing';
  import Navbar from './lib/components/Navbar.svelte';
  import Footer from './lib/components/Footer.svelte';
  import Home from './pages/Home.svelte';
  import Tokens from './pages/Tokens.svelte';
  import About from './pages/About.svelte';
  import Checkout from './pages/Checkout.svelte';
</script>

<div class="app-layout">
  <Router>
    <Navbar />

    <main class="main-content">
      <Route path="/" let:params>
        <Home {params} />
      </Route>
      <Route path="/tokens" let:params>
        <Tokens {params} />
      </Route>
      <Route path="/about" let:params>
        <About {params} />
      </Route>
      <Route path="/checkout" let:params>
        <Checkout {params} />
      </Route>
    </main>

    <Footer />
  </Router>
</div>

<style>
  html, body {
    margin: 0;
    padding: 0;
    height: 100%;
  }

  .app-layout {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  .main-content {
    flex: 1;
    padding: 2rem 1rem;
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
  }
</style>
