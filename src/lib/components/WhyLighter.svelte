<script>
  import SectionLabel from './SectionLabel.svelte';
</script>

<section class="bg-[#f5f5f5] px-6 py-24">
  <div class="max-w-[1400px] mx-auto grid grid-cols-1 lg:grid-cols-12 gap-12">
    <div class="lg:col-span-3">
      <SectionLabel label="Why Lighter" />
    </div>
    
    <div class="lg:col-span-9 grid grid-cols-1 md:grid-cols-2 gap-16">
      <div>
        <h2 class="font-serif text-3xl md:text-4xl leading-tight text-gray-900 mb-6">
          Trade with zero fees while maintaining full Ethereum security
        </h2>
        <p class="text-gray-500 leading-relaxed">
          Our custom ZK rollup proves all operations on-chain, giving you the speed of centralized exchanges with the security and transparency of Ethereum.
        </p>
      </div>
      
      <div class="flex gap-12 items-end pb-2">
        <div class="flex flex-col gap-1">
            <span class="text-xs text-gray-400">Zero trading fees</span>
        </div>
        <div class="flex flex-col gap-1">
            <span class="text-xs text-gray-400">Instant execution</span>
        </div>
      </div>
    </div>
  </div>
</section>
