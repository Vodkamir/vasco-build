<script>
	import { fade, slide } from 'svelte/transition';

	let expandedService = $state(-1);

	const services = [
		{
			title: 'Dry lining',
			icon: 'fa-layer-group',
			image: 'https://images.unsplash.com/photo-1562259949-e8e7689d7828?w=900&h=600&fit=crop',
			alt: 'Smooth freshly finished interior wall',
			description: 'Smooth walls, better insulation and a clean base ready for decorating.',
			details: 'We can line tired or uneven walls, improve thermal performance and leave the surface ready for paint, wallpaper or other finishes.',
			includes: ['Wall lining and boarding', 'Insulation upgrades', 'Jointing and preparation']
		},
		{
			title: 'Outside cladding',
			icon: 'fa-house',
			image: 'https://images.unsplash.com/photo-1503387762-592deb58ef4e?w=900&h=600&fit=crop',
			alt: 'Modern exterior with clean cladding finish',
			description: 'Hard-wearing exterior finishes that protect your property and lift its kerb appeal.',
			details: 'From repairs to complete sections, we fit practical exterior cladding that helps protect your property from the weather and gives it a smarter finish.',
			includes: ['Cladding repairs and replacement', 'Weather-resistant finishes', 'Neat trims and detailing']
		},
		{
			title: 'Property cleaning',
			icon: 'fa-broom',
			image: 'https://images.unsplash.com/photo-1581578731548-c64695cc6952?w=900&h=600&fit=crop',
			alt: 'Professional cleaner preparing a bright room',
			description: 'One-off deep cleans, post-project tidies and spaces that need a reset.',
			details: 'We clear dust, dirt and leftover mess after building work, tenancies or busy periods, helping you get the space back into use quickly.',
			includes: ['Post-project clean-ups', 'Deep cleans and resets', 'Dust and debris removal']
		},
		{
			title: 'Rubbish removal',
			icon: 'fa-truck-ramp-box',
			image: 'https://images.unsplash.com/photo-1530587191325-3db32d826c18?w=900&h=600&fit=crop',
			alt: 'Clean skip and building materials ready for removal',
			description: 'We load, remove and responsibly dispose of waste from your site.',
			details: 'We can take away general site waste, old fixtures and unwanted materials, leaving your property clearer and safer.',
			includes: ['Building and garden waste', 'Old fixtures and materials', 'Loading and responsible disposal']
		},
		{
			title: 'General handyman work',
			icon: 'fa-screwdriver-wrench',
			image: 'https://images.unsplash.com/photo-1581244277943-fe4a9c777189?w=900&h=600&fit=crop',
			alt: 'Handyman using tools on a home repair',
			description: 'Repairs, prep and practical jobs that have been sitting on your list.',
			details: 'Bring us the jobs you have been putting off, from minor repairs and adjustments to preparation work that needs a practical pair of hands.',
			includes: ['Minor repairs and adjustments', 'Fixtures and fittings', 'Preparation and maintenance']
		},
		{
			title: 'Finishing touches',
			icon: 'fa-paint-roller',
			image: 'https://images.unsplash.com/photo-1562259949-e8e7689d7828?w=900&h=600&fit=crop',
			alt: 'Freshly painted room ready to use',
			description: 'Prep, patching and the small details that turn a job into a finished space.',
			details: 'We handle the final preparation, patching and detail work that helps a room or project look complete and ready to enjoy.',
			includes: ['Patching and filling', 'Surface preparation', 'Final checks and tidy-up']
		}
	];

	/** @param {number} index */
	function toggleService(index) {
		expandedService = expandedService === index ? -1 : index;
	}
</script>

<section id="services" class="py-16 md:py-24 bg-white">
	<div class="container mx-auto px-4">
		<div class="text-center mb-16">
			<h2 class="text-3xl md:text-5xl font-bold text-gray-900 mb-4">Work that makes a difference</h2>
			<p class="text-xl text-gray-600">Reliable handyman help for homes, landlords and small businesses.</p>
		</div>
		<div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-6 max-w-6xl mx-auto">
			{#each services as service, index (service.title)}
				<article
					class="bg-gradient-to-br from-orange-50 to-white border-2 border-orange-200 rounded-xl p-6 hover:shadow-xl transition"
				>
					<button
						class="w-full text-left focus:outline-none focus-visible:ring-2 focus-visible:ring-orange-600 focus-visible:ring-offset-2 rounded-lg"
						type="button"
						aria-expanded={expandedService === index}
						aria-controls={`service-details-${index}`}
						onclick={() => toggleService(index)}
					>
						<div class="flex items-start justify-between gap-4">
							<div class="w-16 h-16 bg-orange-600 text-white rounded-lg flex items-center justify-center shrink-0">
								<i class={`fas ${service.icon} text-2xl`}></i>
							</div>
							<i
								class={`fas fa-chevron-down text-orange-600 mt-2 transition-transform ${expandedService === index ? 'rotate-180' : ''}`}
								aria-hidden="true"
							></i>
						</div>
						<h3 class="text-xl font-bold text-gray-900 mt-4 mb-2">{service.title}</h3>
						<p class="text-gray-600">{service.description}</p>
					</button>

					{#if expandedService === index}
						<div
							id={`service-details-${index}`}
							class="border-t border-orange-200 mt-5 pt-5 text-gray-700 overflow-hidden"
							transition:slide={{ duration: 320 }}
						>
							<img
								src={service.image}
								alt={service.alt}
								class="w-full h-40 object-cover rounded-lg mb-4"
								loading="lazy"
							/>
							<div transition:fade={{ duration: 420, delay: 80 }}>
								<p class="leading-relaxed">{service.details}</p>
								<h4 class="font-bold text-gray-900 mt-4 mb-2">This can include:</h4>
								<ul class="space-y-2">
									{#each service.includes as item (item)}
										<li class="flex items-start gap-2">
											<i class="fas fa-check text-orange-600 mt-1" aria-hidden="true"></i>
											<span>{item}</span>
										</li>
									{/each}
								</ul>
							</div>
						</div>
					{/if}
				</article>
			{/each}
		</div>
	</div>
</section>
