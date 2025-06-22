<section id="destinations" class="bg-black text-white px-6 py-24">
	<div class="max-w-7xl mx-auto text-center">
		<h2 class="text-4xl font-extrabold mb-4 text-lime-400">Destinations au Maroc</h2>
		<p class="text-gray-300 mb-12">Découvrez les plus belles destinations à travers le Royaume du Maroc</p>

		<div class="grid gap-8 md:grid-cols-3">
			<!-- Destination Card -->
			{#each [
				{ name: 'Marrakech', img: 'https://www.guidesulysse.com/imageswebp/destinations/iStock-530236509.webp' },
				{ name: 'Chefchaouen', img: 'https://media-cdn.tripadvisor.com/media/attractions-splice-spp-674x446/0a/89/da/2d.jpg' },
				{ name: 'Benslimane', img: 'https://www.sagaphoto.com/bassedefWM/MAOR0010.jpg' }
			] as city}
				<div class="bg-white/5 backdrop-blur rounded-xl overflow-hidden shadow-lg">
					<img src={city.img} alt={city.name} class="h-48 w-full object-cover" />
					<div class="p-4">
						<h3 class="text-xl font-bold text-white">{city.name}</h3>
						<p class="text-gray-400 text-sm">Voyagez vers {city.name}, une destination magique au cœur du Maroc.</p>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
