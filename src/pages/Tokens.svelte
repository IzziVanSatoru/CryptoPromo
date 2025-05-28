<script>
  import { onMount } from 'svelte';
  import { tokenStore } from '../lib/stores/tokenStore';
  import TokenCard from '../lib/components/TokenCard.svelte';

  let loading = true;
  let error = null;

  onMount(async () => {
    try {
      const res = await fetch('/crypto.json');
      if (!res.ok) throw new Error('Gagal mengambil data.');
      const data = await res.json();
      tokenStore.set(data);
    } catch (err) {
      error = err.message;
    } finally {
      loading = false;
    }
  });
</script>

<section class="tokens-section">
  <h2>🔥 Top 10 Crypto Assets</h2>

  {#if loading}
    <p class="status">Loading tokens...</p>
  {:else if error}
    <p class="status error">{error}</p>
  {:else}
    <div class="token-grid">
      {#each $tokenStore as token (token.id)}
        <TokenCard {token} />
      {/each}
    </div>
  {/if}
</section>

<style>
  .tokens-section {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem 1rem;
    text-align: center;
  }

  .tokens-section h2 {
    font-size: 2rem;
    margin-bottom: 2rem;
    color: #1e3c72;
  }

  .status {
    font-size: 1rem;
    color: #444;
  }

  .status.error {
    color: red;
  }

  .token-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
    margin-top: 2rem;
  }
</style>
