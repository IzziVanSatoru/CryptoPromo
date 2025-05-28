<script>
  import { purchaseStore } from '../lib/stores/purchaseStore';
  import { onMount } from 'svelte';
  import { navigate } from 'svelte-routing';

  let purchase = null;

  onMount(() => {
    const unsubscribe = purchaseStore.subscribe(value => {
      purchase = value;
    });

    if (!purchase) {
      // Redirect back if no data
      navigate('/tokens');
    }

    return () => unsubscribe();
  });

  function confirmPurchase() {
    alert(`✅ Purchase confirmed for ${purchase.name} at $${purchase.price}!`);
    // Optionally reset store or push to DB here
    purchaseStore.set(null);
    navigate('/');
  }
</script>

{#if purchase}
  <section class="checkout">
    <h2>🧾 Checkout Summary</h2>
    <div class="summary-card">
      <h3>{purchase.name} ({purchase.symbol})</h3>
      <p>Price: ${purchase.price}</p>
      <button on:click={confirmPurchase}>Confirm Purchase</button>
    </div>
  </section>
{/if}

<style>
  .checkout {
    max-width: 600px;
    margin: 3rem auto;
    text-align: center;
  }

  .summary-card {
    background: #f1f3f8;
    padding: 2rem;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }

  h3 {
    margin-bottom: 1rem;
    color: #1e3c72;
  }

  p {
    font-size: 1.2rem;
    margin-bottom: 1.5rem;
  }

  button {
    padding: 0.6rem 1.5rem;
    background: #2a5298;
    color: white;
    font-weight: bold;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: background 0.3s ease;
  }

  button:hover {
    background: #1e3c72;
  }
</style>
