<script>
  import { navigate } from 'svelte-routing';
  import { purchaseStore } from '../stores/purchaseStore';

  export let token;

  function handleBuy() {
    alert(`You selected ${token.name} (${token.symbol}) for checkout.`);
    purchaseStore.set(token);
    navigate('/checkout');
  }
</script>

<div class="card">
  <div class="card-header">
    <h3>{token.name} <span>({token.symbol})</span></h3>
    <p class="price">💰 ${token.price.toLocaleString()}</p>
  </div>
  <button on:click={handleBuy} class="buy-btn">Buy</button>
</div>

<style>
  .card {
    background: #f9fbff;
    padding: 1.5rem;
    border-radius: 14px;
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
  }

  .card:hover {
    transform: translateY(-6px) scale(1.02);
    box-shadow: 0 12px 30px rgba(0, 0, 0, 0.1);
  }

  .card-header h3 {
    font-size: 1.2rem;
    color: #1e3c72;
    margin-bottom: 0.5rem;
  }

  .card-header span {
    font-size: 0.9rem;
    color: #2a5298;
  }

  .price {
    font-size: 1.1rem;
    font-weight: 600;
    color: #333;
    margin-bottom: 1rem;
  }

  .buy-btn {
    padding: 0.6rem 1.2rem;
    font-weight: bold;
    background-color: #2a5298;
    color: white;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: background 0.3s ease, transform 0.2s ease;
  }

  .buy-btn:hover {
    background-color: #1e3c72;
    transform: scale(1.05);
  }

  @media (max-width: 600px) {
    .card {
      padding: 1rem;
    }

    .buy-btn {
      font-size: 0.9rem;
      padding: 0.5rem 1rem;
    }
  }
</style>
