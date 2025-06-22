<script>
	let isOpen = false;
	const navLinks = [
		{ label: "Accueil", href: "#accueil" },
		{ label: "Destinations", href: "#destinations" },
		{ label: "Offres", href: "#offres" },
		{ label: "À propos", href: "#apropos" }
	];
</script>

<header class="fixed w-full top-0 left-0 z-50 bg-black/80 backdrop-blur border-b border-white/10 text-white">
	<div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
		<!-- Logo -->
		<div class="text-2xl font-bold text-lime-400 tracking-wide">
			HM<span class="text-white">Travels</span>
		</div>

		<!-- Desktop Nav -->
		<nav class="hidden md:flex space-x-8 text-white font-medium">
			{#each navLinks as link}
				<a href={link.href} class="hover:text-lime-400 transition">{link.label}</a>
			{/each}
		</nav>

		<!-- Contact Button -->
		<a
			href="#contact"
			class="hidden md:inline-block bg-lime-400 text-black font-semibold px-5 py-2 rounded-lg hover:bg-lime-300 transition"
		>
			Contact
		</a>

		<!-- Mobile Menu Button -->
		<button on:click={() => (isOpen = !isOpen)} class="md:hidden text-3xl focus:outline-none">
			{isOpen ? '✕' : '☰'}
		</button>
	</div>

	<!-- Mobile Nav Menu -->
	{#if isOpen}
		<nav class="md:hidden bg-black border-t border-white/10 px-6 py-4 space-y-3">
			{#each navLinks as link}
				<a href={link.href} class="block text-white hover:text-lime-400 transition">{link.label}</a>
			{/each}
			<a
				href="#contact"
				class="block bg-lime-400 text-black font-semibold text-center px-5 py-2 rounded-lg mt-2"
			>
				Contact
			</a>
		</nav>
	{/if}
</header>
