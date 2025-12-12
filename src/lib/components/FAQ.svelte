<script lang="ts">
  import { slide } from 'svelte/transition';
  
  interface FAQItem {
    question: string;
    answer: string;
  }

  const faqs: FAQItem[] = [
    { question: "How does Lighter achieve zero-fee trading?", answer: "Lighter uses a custom ZK rollup infrastructure that batches transactions and proves them on Ethereum. This allows us to eliminate trading fees while maintaining full security and verifiability." },
    { question: "What is a ZK rollup?", answer: "A ZK (Zero-Knowledge) rollup is a Layer 2 scaling solution that executes transactions off-chain and posts cryptographic proofs to Ethereum. This gives you the speed of centralized exchanges with the security of Ethereum." },
    { question: "How are my funds secured?", answer: "All operations are cryptographically proven and settled on Ethereum. You maintain full custody of your assets, and every trade is verifiable on-chain. There's no need to trust a centralized entity." },
    { question: "What makes Lighter different from other DEXs?", answer: "Lighter combines zero fees, instant execution, and Ethereum security through custom ZK rollup technology. Unlike traditional DEXs with high gas fees or centralized exchanges requiring trust, Lighter offers the best of both worlds." },
    { question: "Can I verify my trades on-chain?", answer: "Yes, all trades are proven on Ethereum using zero-knowledge proofs. You can verify any transaction through our block explorer or directly on the Ethereum blockchain." },
    { question: "What assets can I trade on Lighter?", answer: "Lighter supports major cryptocurrencies and tokens. Our platform is designed for crypto traders who need instant, low-cost trades in the DeFi ecosystem." },
    { question: "How fast are trades executed?", answer: "Trades are executed instantly off-chain and batched into proofs that are posted to Ethereum. You get sub-second execution with the security of on-chain settlement." }
  ];

  let openIndex: number | null = null;

  function toggle(index: number) {
    openIndex = openIndex === index ? null : index;
  }
</script>

<section class="bg-[#f5f5f5] px-6 py-24">
  <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-12 gap-12">
    <div class="lg:col-span-4">
      <h2 class="font-serif text-4xl text-gray-900 mb-6">
        Frequently asked questions
      </h2>
      <a href="/" class="text-sm text-gray-900 border-b border-gray-300 pb-0.5 hover:border-black transition-colors">See all support</a>
    </div>
    
    <div class="lg:col-span-8">
      <div class="border-t border-gray-200">
        {#each faqs as faq, i}
          <div class="border-b border-gray-200">
            <button 
              class="w-full py-6 flex justify-between items-center text-left hover:bg-gray-50 transition-colors"
              on:click={() => toggle(i)}
            >
              <span class="text-lg text-gray-800">{faq.question}</span>
              <span class="text-2xl font-light text-gray-400 ml-4">
                {openIndex === i ? '−' : '+'}
              </span>
            </button>
            {#if openIndex === i}
              <div transition:slide class="pb-6 text-gray-500 leading-relaxed">
                {faq.answer}
              </div>
            {/if}
          </div>
        {/each}
      </div>
    </div>
  </div>
</section>
