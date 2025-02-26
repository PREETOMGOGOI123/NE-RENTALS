<script>
	const availableBikes = [
		{
			id: 'M001',
			name: 'Royal Enfield Himalayan',
			image:
				'https://images.unsplash.com/photo-1609174470568-ac0c96458a67?q=80&w=2071&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
			price: '1500/day',
			type: 'Adventure',
			status: 'Available',
			location: 'XYZ',
			cc: '411cc',
			features: ['All-Terrain', 'ABS', 'Digital Navigation']
		},
		{
			id: 'M002',
			name: 'Hero XPulse 200',
			image:
				'https://images.unsplash.com/photo-1648131728440-14d0225c16c3?q=80&w=1976&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
			price: '1000/day',
			type: 'Adventure',
			status: 'Available',
			location: 'XYZ',
			cc: '200cc',
			features: ['Off-Road Ready', 'LED Headlamp', 'Turn-by-Turn Navigation']
		},
		{
			id: 'M003',
			name: 'City Commutes',
			image:
				'https://images.unsplash.com/photo-1724992638710-3e365cafc968?q=80&w=2140&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
			price: '500/day',
			type: 'City Commuter',
			status: 'Available',
			location: 'XYZ',
			cc: '125cc',
			features: ['Economic', 'Comfortable', 'Low Maintenance']
		},
		{
			id: 'M004',
			name: 'Scooters',
			image:
				'https://images.unsplash.com/photo-1591517487866-e7c7bf9896fb?q=80&w=1935&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D',
			price: '400/day',
			type: 'City Commuter',
			status: 'Available',
			location: 'XYZ',
			cc: '125cc',
			features: ['Economic', 'Easy to Ride', 'Storage Space']
		}
	];
</script>

<section id="available" class="w-full mx-auto rounded-md md:p-10 md:my-[10rem]">
	<div class="w-full mx-auto px-4">
		<h2 class="mb-18 text-center text-3xl font-bold">Available Motorcycles</h2>

		<!-- Motorcycle Grid -->
        <div class="w-full flex gap-20 overflow-x-auto px-10 pb-8 shadow-lg rounded-md">
			<!-- {/* Motorcycle Grid */} -->
			{#each availableBikes as bike (bike.id)}
				<div class="card bg-base-100 shadow-xl transition-shadow duration-300 hover:shadow-2xl">
					<figure class="relative md:h-64 md:w-[25rem] w-full h-40">
						<img src={bike.image} alt={bike.name} class="h-full w-full object-cover" />
						<div class="absolute top-4 right-4">
							<span class="badge badge-success">{bike.status}</span>
						</div>
					</figure>
					<div class="card-body flex flex-col justify-between">
						<h3 class="card-title flex justify-between">
							{bike.name}
							<div class="badge p-5">{bike.type}</div>
						</h3>
						<div class="md:space-y-2">
							<p class="text-xl font-bold">₹{bike.price}</p>
							<p class="text-sm">📍 {bike.location}</p>
							<p class="text-sm">🔧 {bike.cc}</p>
							<div class="mt-2 flex flex-wrap gap-2">
								{#each bike.features as feature}
									<span class="badge badge-outline p-2">{feature}</span>
								{/each}
							</div>
						</div>
						<div class="card-actions mt-4 justify-end">
							<a
								href="https://docs.google.com/forms/d/e/1FAIpQLScrUsH_h5nD6IIERLW_fNccs0zTxMm-y2fqeXJGc6Nd1HeaEw/viewform?usp=sharing"
								class="btn btn-neutral text-white transform transition-transform hover:scale-105 rounded-md"
								target="_blank"
								rel="noopener noreferrer"
							>
								Rent Now
							</a>
						</div>
					</div>
				</div>
			{/each}
		</div>
	</div>
</section>
