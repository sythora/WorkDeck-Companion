<script>
  import "../app.css";
  import { createEventDispatcher } from 'svelte';
  import { fade, fly } from 'svelte/transition';

  const dispatch = createEventDispatcher();

  function handleConnect() {
    dispatch('connect');
  }
</script>

<div class="flex items-center justify-center min-h-screen bg-[#0a0a0a] text-[#e0e0e0]">
  <div class="text-center max-w-[400px]" in:fade={{ duration: 600 }}>
    <img
      src="/assets/logo.png"
      alt="WorkDeck Logo"
      class="w-[120px] h-[120px] mb-8 rounded-[20px] mx-auto animate-float"
      in:fly={{ y: -50, duration: 800, delay: 200 }}
    />
    <h1
      class="text-[42px] font-bold mb-2.5 text-white leading-tight"
      in:fly={{ y: 20, duration: 600, delay: 400 }}
    >
      Meet Work<span class="text-transparent bg-clip-text bg-gradient-to-r from-purple-400 to-pink-400">Deck</span> Companion
    </h1>
    <p
      class="text-lg text-[#999] mb-10"
      in:fly={{ y: 20, duration: 600, delay: 500 }}
    >
      Your DIY StreamDeck.
    </p>
    <button
      class="group relative bg-gradient-to-br from-[#667eea] to-[#764ba2] text-white border-none py-4 px-12 text-base font-semibold rounded-xl cursor-pointer transition-all duration-200 hover:-translate-y-1 hover:shadow-[0_12px_30px_rgba(102,126,234,0.4)] active:translate-y-0 overflow-hidden"
      on:click={handleConnect}
      in:fly={{ y: 20, duration: 600, delay: 600 }}
    >
      <span class="relative z-10">Connect Your WorkDeck</span>
      <div class="absolute inset-0 bg-gradient-to-r from-purple-600 to-pink-600 opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
    </button>
  </div>
</div>

<style>
  @keyframes float {
    0%, 100% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
  }

  .animate-float {
    animation: float 3s ease-in-out infinite;
  }
</style>
