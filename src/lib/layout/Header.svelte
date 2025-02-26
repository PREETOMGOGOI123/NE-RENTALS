<script>
	import { base } from '$app/paths';
	let isMenuOpen = $state(false);
</script>

<section class="header bg-neutral text-neutral-content">
	<nav class="navbar top-0 z-50 px-4 py-5 md:px-10">
		<div class="navbar-start">
			<a class="btn btn-outline logo text-xl font-black normal-case italic md:text-3xl" href="{base}/"
				>NE RENTALS</a
			>
		</div>

		<!-- Mobile menu button  -->
		<div class="navbar-end lg:hidden">
			<!-- svelte-ignore a11y_consider_explicit_label -->
			<button class="btn btn-ghost" onclick={() => (isMenuOpen = !isMenuOpen)}>
				<svg
					xmlns="http://www.w3.org/2000/svg"
					fill="none"
					viewBox="0 0 24 24"
					stroke="currentColor"
					class="h-6 w-6"
				>
					<path
						strokeLinecap="round"
						strokeLinejoin="round"
						strokeWidth={2}
						d="M4 6h16M4 12h16m-7 6h7"
					/>
				</svg>
			</button>
		</div>

		<!-- /* Desktop menu */ -->
		<div class="navbar-center hidden lg:flex">
			<ul class="menu menu-horizontal gap-10 px-1">
				<li><a href="{base}/#available" class="btn btn-accent btn-outline">View available Bikes</a></li>
			</ul>
		</div>
		<div class="navbar-end hidden lg:flex">
			<p class="text-sm">☎️ +91 8011127009</p>
		</div>
	</nav>

	<!-- /* Mobile menu dropdown */ -->
	{#if isMenuOpen}
		<div class="bg--100 fixed top-[90px] right-0 left-0 z-50 p-4 shadow-lg lg:hidden">
			<div class="flex flex-col gap-4">
				<p class="btn btn-outline w-full">☎️ +91 8011127009</p>
				<a href="{base}/#list-bikes" class="btn w-full" onclick={() => (isMenuOpen = false)}
					>List Your Bike</a
				>
				<a href="{base}/#available" class="btn w-full" onclick={() => (isMenuOpen = false)}>View Bikes</a>
			</div>
		</div>
	{/if}
</section>

<style>
	.logo {
		background: url(https://plus.unsplash.com/premium_photo-1663090593977-9923cc536f3b?q=80&w=2070&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D);
		-webkit-background-clip: text;
		background-clip: text;
		-webkit-text-fill-color: transparent;
		background-size: contain;
		background-position: center;
	}

	/* Add these to your existing styles */
	@media (max-width: 1023px) {
		.navbar {
			padding-left: 1rem;
			padding-right: 1rem;
		}
	}

	/* Animation for mobile menu */
	@keyframes slideDown {
		from {
			transform: translateY(-100%);
			opacity: 0;
		}
		to {
			transform: translateY(0);
			opacity: 1;
		}
	}

	.fixed {
		animation: slideDown 0.3s ease-out;
	}
</style>
