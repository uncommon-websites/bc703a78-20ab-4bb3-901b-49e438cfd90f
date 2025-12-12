<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  
  // Icons
  const ArrowRight = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="m12 5 7 7-7 7"/></svg>`;
  const PlayCircle = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"/><polygon points="10 8 16 12 10 16 10 8"/></svg>`;
  const ChevronLeft = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m15 18-6-6 6-6"/></svg>`;
  const ChevronRight = `<svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m9 18 6-6-6-6"/></svg>`;
  const Check = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>`;
  const Plus = `<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M5 12h14"/><path d="M12 5v14"/></svg>`;
  const Instagram = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>`;
  const LinkedIn = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 8a6 6 0 0 1 6 6v7h-4v-7a2 2 0 0 0-2-2 2 2 0 0 0-2 2v7h-4v-7a6 6 0 0 1 6-6z"/><rect width="4" height="12" x="2" y="9"/><circle cx="4" cy="4" r="2"/></svg>`;
  const XIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 18 12"/></svg>`;

  // Data
  const heroImages = [
    "/generated/image-person-sleeping-peacefully-in-comfortabl-1765567495474-0.webp",
    "/generated/image-professional-waking-up-in-morning-feelin-1765567700973-0.webp",
    "/generated/image-active-adult-doing-morning-yoga-or-exerc-1765567498029-2.webp",
    "/generated/image-person-relaxing-in-evening-with-herbal-t-1765567500345-3.webp",
    "/generated/image-athlete-recovering-after-workout-relaxed-1765567502770-4.webp",
    "/generated/image-mature-adult-reading-peacefully-before-b-1765567505009-5.webp"
  ];

  const benefitCards = [
    {
      title: "Deep, restorative sleep.",
      desc: "Fall asleep naturally and stay asleep through the night with our melatonin-free formula powered by magnesium glycinate and L-Theanine.",
      image: "/generated/image-person-in-peaceful-deep-sleep-with-seren-1765567703279-1.webp"
    },
    {
      title: "Wake up refreshed.",
      desc: "Experience morning clarity without grogginess. Our unique nitric oxide blend supports overnight recovery and circulation for better mornings.",
      image: "/generated/image-athletic-person-looking-energized-and-re-1765567509812-8.webp"
    },
    {
      title: "Natural ingredients only.",
      desc: "Plant-based formula with organic fermented beetroot, tart cherry, and lemon balm. Third-party tested, vegan, and made in the USA.",
      image: "/generated/image-natural-supplement-powder-in-glass-with--1765567512137-9.webp"
    }
  ];

  const steps = [
    {
      step: 1,
      title: "Order your Sleep Habits powder.",
      desc: "Choose your quantity on Amazon. Get volume discounts: 10% on 2 containers, 15% on 3, or 20% on 4. Prime eligible with free delivery.",
      image: "plan"
    },
    {
      step: 2,
      title: "Mix one scoop before bed.",
      desc: "Blend one scoop with 8-10oz of water 30-60 minutes before sleep. Enjoy the natural cherry pomegranate flavor sweetened with monk fruit.",
      image: "schedule"
    },
    {
      step: 3,
      title: "Feel the difference.",
      desc: "Experience easier sleep onset, deeper rest, and reduced racing thoughts. Most users notice improvements within the first week.",
      image: "results"
    },
    {
      step: 4,
      title: "Wake up refreshed.",
      desc: "No morning grogginess or dependency. Just natural clarity and energy to start your day right.",
      image: "notes"
    },
    {
      step: 5,
      title: "Build your sleep routine.",
      desc: "Consistent use supports your natural sleep-wake cycle. Pair with our nasal strips for complete sleep optimization.",
      image: "improve"
    }
  ];

  const faqs = [
    "How is Sleep Habits different from melatonin supplements?",
    "What are the key ingredients and how do they work?",
    "Will I feel groggy in the morning?",
    "How long does it take to see results?",
    "Is Sleep Habits safe for long-term use?",
    "Can I take Sleep Habits with other supplements?"
  ];
</script>

<Header />

<main class="w-full overflow-x-hidden">
  <!-- Hero Section -->
  <section class="pt-32 pb-16 md:pt-40 md:pb-24 px-6 text-center max-w-7xl mx-auto">
    <h1 class="text-4xl md:text-6xl lg:text-7xl font-medium tracking-tight text-[#1A1A1A] mb-6 leading-[1.1]">
      Restorative sleep.<br />Morning clarity.
    </h1>
    <p class="text-gray-600 text-lg md:text-xl max-w-3xl mx-auto mb-10 leading-relaxed font-light">
      The first sleep powder powered by plant-based nitrates and magnesium glycinate. Fall asleep naturally, recover overnight, wake up refreshed—no melatonin, no grogginess.
    </p>
    <button class="bg-[#1A1A1A] text-white px-8 py-3.5 rounded-sm font-medium hover:bg-black transition-colors">
      Shop now on Amazon
    </button>
  </section>

  <!-- Hero Images Scroll -->
  <div class="w-full overflow-x-auto pb-12 hide-scrollbar">
    <div class="flex gap-4 px-6 min-w-max">
      {#each heroImages as img, i}
        <div class="relative w-48 h-64 md:w-64 md:h-80 rounded-3xl overflow-hidden flex-shrink-0">
          <img src={img} alt="Lifestyle" class="w-full h-full object-cover" />
        </div>
      {/each}
    </div>
  </div>

  <!-- Product Feature Section -->
  <section class="py-20 px-6 max-w-7xl mx-auto" id="ingredients">
    <div class="bg-white rounded-[40px] p-8 md:p-16 flex flex-col md:flex-row items-center gap-12 shadow-sm">
      <!-- Product Image -->
      <div class="w-full md:w-1/2 flex justify-center">
        <div class="relative w-full max-w-md aspect-square rounded-3xl overflow-hidden">
          <img src="/generated/image-close-up-of-natural-ingredients---beetro-1765567507407-6.webp" alt="Natural ingredients" class="w-full h-full object-cover" />
        </div>
      </div>
      
      <!-- Content -->
      <div class="w-full md:w-1/2 space-y-6">
        <h2 class="text-3xl md:text-4xl font-medium leading-tight text-[#1A1A1A]">
          Powered by nature's best sleep ingredients.
        </h2>
        <p class="text-gray-600 leading-relaxed">
          Our proprietary formula combines clinical dosing of magnesium glycinate (200mg), L-Theanine (300mg), glycine (1g), organic lemon balm (300mg), and organic tart cherry (300mg) with plant-based nitrates from organic fermented beetroot, red spinach extract, and pomegranate.
        </p>
        <ul class="space-y-3">
          <li class="flex items-start gap-3 text-sm text-gray-700">
            <span class="mt-0.5 text-primary-600">{@html Check}</span>
            Third-party tested for quality and safety
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-700">
            <span class="mt-0.5 text-primary-600">{@html Check}</span>
            Made in USA in GMP compliant facility
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-700">
            <span class="mt-0.5 text-primary-600">{@html Check}</span>
            Vegan, gluten-free, no artificial ingredients
          </li>
        </ul>
      </div>
    </div>
  </section>

  <!-- Value Proposition -->
  <section class="py-16 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-12 items-start">
      <h2 class="text-3xl md:text-5xl font-medium tracking-tight text-[#1A1A1A] leading-tight">
        Sleep better without the melatonin trap.
      </h2>
      <p class="text-gray-600 text-lg font-light leading-relaxed">
        Melatonin causes grogginess and dependency. Sleep Habits takes a different approach—supporting your body's natural sleep mechanisms while enhancing overnight recovery. Wake up feeling truly rested, not sedated.
      </p>
    </div>
  </section>

  <!-- Benefit Cards -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-3 gap-6">
      {#each benefitCards as card}
        <div class="relative h-[480px] rounded-3xl overflow-hidden group">
          <img src={card.image} alt={card.title} class="absolute inset-0 w-full h-full object-cover transition-transform duration-700 group-hover:scale-105" />
          <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-black/20 to-transparent"></div>
          <div class="absolute bottom-0 left-0 right-0 p-8 text-white">
            <h3 class="text-2xl font-medium mb-3">{card.title}</h3>
            <p class="text-white/80 text-sm leading-relaxed font-light">{card.desc}</p>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Testimonial -->
  <section class="py-24 px-6 max-w-4xl mx-auto text-center">
    <blockquote class="text-2xl md:text-3xl font-medium leading-relaxed text-[#1A1A1A] mb-8">
      "After years of struggling with melatonin dependency, Sleep Habits has been a game-changer. I fall asleep naturally, sleep through the night, and wake up actually refreshed. No grogginess, no foggy mornings—just better sleep."
    </blockquote>
    <div class="flex flex-col items-center gap-3">
      <img src="/generated/image-happy-professional-in-their-30s-40s-genu-1765567514547-10.webp" alt="Customer" class="w-12 h-12 rounded-full object-cover" />
      <div class="text-center">
        <div class="font-medium text-sm">Sarah M.</div>
        <div class="text-gray-500 text-xs">Verified Amazon Customer</div>
      </div>
    </div>
  </section>

  <!-- Stats Grid -->
  <section class="py-12 px-6 max-w-7xl mx-auto border-t border-gray-200">
    <div class="grid md:grid-cols-3 gap-8 text-center md:text-left">
      <div>
        <h3 class="text-xl font-medium mb-2">30 servings per container.</h3>
        <p class="text-gray-500 text-sm font-light">A full month's supply of restorative sleep. Mix one scoop with water 30-60 minutes before bed.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">Made in USA.</h3>
        <p class="text-gray-500 text-sm font-light">Manufactured in GMP compliant facilities. Third-party tested for quality and safety.</p>
      </div>
      <div>
        <h3 class="text-xl font-medium mb-2">4.4 out of 5 stars.</h3>
        <p class="text-gray-500 text-sm font-light">Rated highly by customers on Amazon. Join thousands experiencing better sleep.</p>
      </div>
    </div>
  </section>

  <!-- How it works -->
  <section class="py-20 px-6 max-w-7xl mx-auto">
    <div class="mb-16 max-w-md">
      <h2 class="text-4xl font-medium mb-6">How it works.</h2>
      <p class="text-gray-600 font-light">Simple, natural, effective. Order on Amazon, mix one scoop before bed, and experience the difference. No complicated routines—just better sleep and brighter mornings.</p>
    </div>

    <div class="space-y-6">
      {#each steps as step}
        <div class="bg-white rounded-[40px] p-8 md:p-12 flex flex-col items-center text-center max-w-2xl mx-auto shadow-sm">
          <div class="w-full text-left mb-8">
            <span class="inline-block w-8 h-8 rounded-full border border-gray-200 text-center leading-8 text-sm font-medium mb-4">{step.step}</span>
            <h3 class="text-2xl font-medium mb-3">{step.title}</h3>
            <p class="text-gray-500 font-light text-sm max-w-lg">{step.desc}</p>
          </div>
          
          <!-- Phone Mockup for Step -->
          <div class="relative w-[240px] h-[480px] bg-black rounded-[35px] border-[6px] border-black shadow-xl overflow-hidden mt-4">
             <div class="absolute top-0 left-0 right-0 h-5 bg-black z-20 flex justify-center">
                <div class="w-16 h-3 bg-black rounded-b-lg"></div>
             </div>
             <div class="w-full h-full bg-white pt-8 px-3 overflow-hidden">
                <!-- Dynamic Content based on step -->
                {#if step.image === 'plan'}
                  <div class="space-y-3 mt-4">
                    <div class="p-3 border rounded-xl border-black bg-gray-50">
                      <div class="font-bold text-xs mb-1">Optimal ID</div>
                      <div class="h-1 w-full bg-gray-200 rounded"></div>
                    </div>
                    <div class="p-3 border rounded-xl border-gray-200">
                       <div class="font-bold text-xs mb-1 text-gray-400">Essential</div>
                       <div class="h-1 w-full bg-gray-100 rounded"></div>
                    </div>
                  </div>
                {:else if step.image === 'schedule'}
                   <div class="mt-4">
                     <div class="text-center font-bold mb-4">Appointment</div>
                     <div class="bg-gray-100 h-32 rounded-xl mb-3 flex items-center justify-center text-xs text-gray-400">Map View</div>
                     <button class="w-full bg-black text-white text-xs py-2 rounded-lg">Confirm</button>
                   </div>
                {:else if step.image === 'results'}
                   <div class="bg-black h-full -mx-3 -mt-8 pt-10 px-3 text-white">
                      <div class="text-center mb-6">
                        <div class="w-12 h-12 bg-gray-700 rounded-full mx-auto mb-2"></div>
                        <div class="text-sm font-bold">Grace Parker</div>
                      </div>
                      <div class="space-y-2">
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                         <div class="bg-gray-800 p-2 rounded-lg h-10"></div>
                      </div>
                   </div>
                {:else if step.image === 'notes'}
                   <div class="mt-4 space-y-3">
                      <div class="font-bold text-sm">Health Status</div>
                      <div class="text-[10px] text-gray-500 leading-relaxed">
                        You usually make smart choices for your health through regular exercise...
                      </div>
                      <div class="bg-gray-50 p-2 rounded text-[10px] text-gray-600">
                        Since your diet lacks enough fruits and vegetables...
                      </div>
                   </div>
                {:else}
                   <div class="mt-4 flex flex-col h-full">
                      <div class="flex-1">
                        <div class="bg-gray-100 p-2 rounded-lg rounded-tl-none text-[10px] mb-2 max-w-[80%]">
                          What benefits can I get by bringing ApoB closer to the optimal range?
                        </div>
                        <div class="bg-blue-50 p-2 rounded-lg rounded-tr-none text-[10px] ml-auto max-w-[80%]">
                          By lowering ApoB, you reduce the number of cholesterol-carrying particles...
                        </div>
                      </div>
                      <div class="h-10 border-t mt-2"></div>
                   </div>
                {/if}
             </div>
          </div>
        </div>
      {/each}
    </div>
  </section>

  <!-- Dark Cards Section -->
  <section class="py-8 px-6 max-w-7xl mx-auto">
    <div class="grid md:grid-cols-2 gap-6">
      <!-- Quality Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Quality you can trust.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Third-party tested and GMP certified for your safety.</h2>
        </div>
        <!-- Abstract Quality Visual -->
        <div class="absolute inset-0 flex items-center justify-center opacity-20 mt-20">
           <svg viewBox="0 0 200 200" class="w-full h-full text-gray-500 fill-current">
              <circle cx="100" cy="100" r="60" stroke="currentColor" stroke-width="2" fill="none" />
              <circle cx="100" cy="100" r="40" stroke="currentColor" stroke-width="2" fill="none" />
              <circle cx="100" cy="100" r="20" stroke="currentColor" stroke-width="2" fill="none" />
              <path d="M85 100 L95 110 L115 85" stroke="currentColor" stroke-width="3" fill="none" />
           </svg>
        </div>
      </div>

      <!-- Natural Ingredients Card -->
      <div class="bg-[#111] rounded-[40px] p-8 md:p-12 text-white min-h-[500px] flex flex-col relative overflow-hidden">
        <div class="relative z-10">
          <h3 class="text-sm font-medium text-gray-400 mb-2">Plant-powered formula.</h3>
          <h2 class="text-2xl md:text-3xl font-medium max-w-xs">Organic ingredients sourced from nature's best.</h2>
        </div>
        <!-- Plant Visual -->
        <div class="absolute inset-0 flex items-center justify-center mt-20 overflow-hidden opacity-10">
           <div class="text-8xl">🌿</div>
        </div>
      </div>
    </div>
  </section>

  <!-- Pricing Section -->
  <section class="py-24 px-6 max-w-7xl mx-auto" id="buy">
    <div class="text-center mb-16">
      <h2 class="text-3xl md:text-4xl font-medium mb-4">Better sleep starts tonight.</h2>
      <p class="text-gray-500 font-light max-w-2xl mx-auto">Premium sleep support made affordable. Available on Amazon with Prime delivery and volume discounts for consistent results.</p>
    </div>

    <div class="grid md:grid-cols-2 gap-6 max-w-4xl mx-auto">
      <!-- Single Container -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col">
        <div class="w-12 h-12 bg-gray-100 rounded-full mb-6 flex items-center justify-center text-2xl">💤</div>
        <h3 class="text-2xl font-medium mb-1">Single Container</h3>
        <p class="text-sm text-gray-500 mb-6">Try it for a month.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">$36.00</span>
          <span class="text-gray-400 text-sm line-through ml-2">$44.00</span>
          <div class="text-[10px] text-primary-600 mt-1 font-medium">30 servings • $1.20 per serving</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            30 servings of restorative sleep support
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Natural cherry pomegranate flavor
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Amazon Prime free delivery
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Third-party tested for quality
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Buy on Amazon</button>
      </div>

      <!-- Multi-Pack -->
      <div class="bg-white rounded-[32px] p-8 flex flex-col relative overflow-hidden">
        <div class="absolute top-0 right-0 bg-[#FFF8E1] px-4 py-1 rounded-bl-xl text-xs font-medium text-orange-800">Best Value</div>
        <div class="w-12 h-12 bg-primary-100 rounded-full mb-6 flex items-center justify-center text-2xl">✨</div>
        <h3 class="text-2xl font-medium mb-1">Multi-Pack</h3>
        <p class="text-sm text-gray-500 mb-6">Save with volume discounts.</p>
        <div class="mb-8">
          <span class="text-2xl font-medium">Save up to 20%</span>
          <div class="text-[10px] text-primary-600 mt-1 font-medium">10% off 2 items • 15% off 3 items • 20% off 4 items</div>
        </div>
        <ul class="space-y-4 mb-8 flex-1">
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Stock up and save on every order
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Never run out of your sleep support
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Best value for consistent results
          </li>
          <li class="flex items-start gap-3 text-sm text-gray-600 font-light">
            <span class="mt-0.5 text-black">{@html Check}</span>
            Free Prime delivery on all orders
          </li>
        </ul>
        <button class="w-full bg-[#1A1A1A] text-white py-3 rounded-sm font-medium hover:bg-black transition-colors">Buy on Amazon</button>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="py-20 px-6 max-w-3xl mx-auto" id="faq">
    <h2 class="text-3xl font-medium text-center mb-12">Your questions answered.</h2>
    <div class="space-y-4">
      {#each faqs as question}
        <div class="border-b border-gray-200 py-4 flex justify-between items-center cursor-pointer group hover:bg-gray-50/50 transition-colors px-2">
          <span class="text-sm md:text-base font-medium text-gray-800">{question}</span>
          <span class="text-gray-400 group-hover:text-black transition-colors">{@html Plus}</span>
        </div>
      {/each}
    </div>
    <div class="mt-12 text-center">
      <button class="border border-gray-300 px-6 py-3 rounded-sm text-xs font-medium hover:bg-gray-50 transition-colors">
        View all Frequently Asked Questions
      </button>
    </div>
  </section>

  <!-- Footer -->
  <footer class="py-16 px-6 border-t border-gray-200 bg-[#F9F8F6]">
    <div class="max-w-7xl mx-auto">
      <div class="flex flex-col md:flex-row justify-between items-start md:items-center gap-8 mb-16">
        <div class="flex items-center gap-2">
           <span class="font-bold text-lg tracking-wide">Sleep Habits</span>
        </div>
        
        <nav class="flex flex-wrap gap-6 md:gap-8 text-xs font-medium text-gray-600">
          <a href="#ingredients" class="hover:text-black">Ingredients</a>
          <a href="#faq" class="hover:text-black">FAQ</a>
          <a href="#" class="hover:text-black">Blog</a>
          <a href="#" class="hover:text-black">Terms & Conditions</a>
          <a href="#" class="hover:text-black">Privacy Policy</a>
        </nav>

        <div class="flex gap-4 text-gray-800">
          <a href="#" class="hover:text-black">{@html XIcon}</a>
          <a href="#" class="hover:text-black">{@html Instagram}</a>
          <a href="#" class="hover:text-black">{@html LinkedIn}</a>
        </div>
      </div>

      <div class="text-[10px] text-gray-400 leading-relaxed max-w-5xl">
        <p class="mb-2">Sleep Habits products are dietary supplements and are not intended to diagnose, treat, cure, or prevent any disease. These statements have not been evaluated by the Food and Drug Administration. Results may vary. If you are pregnant, nursing, taking medication, or have a medical condition, consult your healthcare provider before use. Not intended for children under 18.</p>
        <p>Individual results may vary. The testimonials and examples provided are not typical results and your results may differ. Always consult with a qualified healthcare professional before starting any supplement regimen.</p>
        <p class="mt-2">Sleep Habits is sold through Amazon.com. Pricing and availability subject to change. Amazon Prime benefits apply where available.</p>
      </div>
    </div>
  </footer>
</main>

<style>
  :global(body) {
    background-color: #F9F8F6;
    font-family: 'Inter', sans-serif;
  }
  
  .hide-scrollbar::-webkit-scrollbar {
    display: none;
  }
  .hide-scrollbar {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>

