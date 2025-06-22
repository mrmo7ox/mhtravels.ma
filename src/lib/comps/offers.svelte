<section id="offres" class="bg-neutral-900 text-white px-6 py-24">
	<div class="max-w-7xl mx-auto text-center">
		<h2 class="text-4xl font-extrabold mb-4 text-lime-400">Nos Offres</h2>
		<p class="text-gray-300 mb-12">Choisissez une expérience inoubliable adaptée à votre style</p>

		<div class="grid gap-8 md:grid-cols-3">
			<!-- Offer Cards -->
			{#each [
				{ title: 'Week-end à Marrakech', price: '1.500 DH', desc: '2 nuits à l’hôtel + visite guidée de la Médina' },
				{ title: 'Aventure dans Benslimane', price: '2.900 DH', desc: '3 jours à Benslimane avec balade à dos de dromadaire' },
				{ title: 'Évasion à Chefchaouen', price: '1.200 DH', desc: '2 jours dans la perle bleue du nord' }
			] as offer}
				<div class="bg-white/5 backdrop-blur rounded-xl p-6 border border-white/10">
					<h3 class="text-xl font-bold text-white">{offer.title}</h3>
					<p class="text-lime-300 font-semibold text-lg mt-2">{offer.price}</p>
					<p class="text-gray-400 mt-2">{offer.desc}</p>
					<a href="#contact" class="inline-block mt-4 px-4 py-2 border border-lime-400 text-lime-400 rounded hover:bg-lime-400 hover:text-black transition">
						Réserver
					</a>
				</div>
			{/each}
		</div>
	</div>
</section>
