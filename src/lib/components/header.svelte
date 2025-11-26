<script>
	let aaaa = $state(false);

	// function toggleMenu() {
	// aaaa = !aaaa;
	// }
</script>

<header class="bg-white shadow-md sticky top-0 z-50">
	<nav class="container mx-auto px-4 py-4">
		<div class="flex items-center justify-between">
			<div class="flex items-center space-x-2">
				<i class="fas fa-car text-orange-600 text-3xl"></i>
				<span class="text-2xl font-bold text-gray-800"
					>ScrapCar<span class="text-orange-600">Pro</span></span
				>
			</div>
			<div class="hidden md:flex items-center space-x-8">
				<a href="#how-it-works" class="text-gray-700 hover:text-orange-600 transition"
					>How It Works</a
				>
				<a href="#services" class="text-gray-700 hover:text-orange-600 transition">Services</a>
				<a href="#why-us" class="text-gray-700 hover:text-orange-600 transition">Why Choose Us</a>
				<a href="#contact" class="text-gray-700 hover:text-orange-600 transition">Contact</a>
				<a
					href="#quote"
					class="bg-orange-600 text-white px-6 py-2 rounded-lg hover:bg-orange-700 transition font-semibold"
					>Get Free Quote</a
				>
			</div>
			<!-- <button onclick={toggleMenu} class="md:hidden text-gray-700 text-2xl">
				<i class="fas fa-bars"></i>
			</button> -->
		</div>
		{#if aaaa}
			<div class="md:hidden mt-4 space-y-2">
				<a href="#how-it-works" class="block text-gray-700 hover:text-orange-600 transition py-2"
					>How It Works</a
				>
				<a href="#services" class="block text-gray-700 hover:text-orange-600 transition py-2"
					>Services</a
				>
				<a href="#why-us" class="block text-gray-700 hover:text-orange-600 transition py-2"
					>Why Choose Us</a
				>
				<a href="#contact" class="block text-gray-700 hover:text-orange-600 transition py-2"
					>Contact</a
				>
				<a
					href="#quote"
					class="block bg-orange-600 text-white px-6 py-2 rounded-lg hover:bg-orange-700 transition font-semibold text-center"
					>Get Free Quote</a
				>
			</div>
		{/if}
	</nav>
</header>
