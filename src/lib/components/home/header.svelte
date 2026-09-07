<script>
	let isMenuOpen = $state(false);

	function toggleMenu() {
		isMenuOpen = !isMenuOpen;
	}
</script>

<header class="bg-white shadow-md sticky top-0 z-50">
	<nav class="container mx-auto px-4 py-4">
		<div class="flex items-center justify-between">
			<div class="flex items-center space-x-2">
				<i class="fas fa-hammer text-orange-600 text-3xl"></i>
				<span class="text-2xl font-bold text-gray-800">Vasco<span class="text-orange-600">Build</span></span>
			</div>
			<div class="hidden md:flex items-center gap-8">
				<a href="#how-it-works" class="text-gray-700 hover:text-orange-600 transition"
					>How It Works</a
				>
				<a href="#services" class="text-gray-700 hover:text-orange-600 transition">Services</a>
				<a href="#why-us" class="text-gray-700 hover:text-orange-600 transition">Why VascoBuild</a>
				<a href="#contact" class="text-gray-700 hover:text-orange-600 transition">Contact</a>
				<a
					href="tel:07849419079"
					class="bg-orange-600 text-white px-6 py-2 rounded-lg hover:bg-orange-700 transition font-semibold"
					>Call 078494 19079</a
				>
			</div>
			<button onclick={toggleMenu} aria-label="Toggle navigation menu" class="md:hidden text-gray-700 text-2xl">
				<i class="fas fa-bars"></i>
			</button>
		</div>
		{#if isMenuOpen}
			<div class="md:hidden mt-4 space-y-2">
				<a href="#how-it-works" onclick={() => (isMenuOpen = false)} class="block text-gray-700 hover:text-orange-600 transition py-2"
					>How It Works</a
				>
				<a href="#services" onclick={() => (isMenuOpen = false)} class="block text-gray-700 hover:text-orange-600 transition py-2"
					>Services</a
				>
				<a href="#why-us" onclick={() => (isMenuOpen = false)} class="block text-gray-700 hover:text-orange-600 transition py-2"
					>Why VascoBuild</a
				>
				<a href="#contact" onclick={() => (isMenuOpen = false)} class="block text-gray-700 hover:text-orange-600 transition py-2"
					>Contact</a
				>
				<a
					href="tel:07849419079"
					onclick={() => (isMenuOpen = false)}
					class="block bg-orange-600 text-white px-6 py-2 rounded-lg hover:bg-orange-700 transition font-semibold text-center"
					>Call 078494 19079</a
				>
			</div>
		{/if}
	</nav>
</header>
