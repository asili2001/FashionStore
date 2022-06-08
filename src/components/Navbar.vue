<template>
	<nav class="flex flex-col font-gupter">
		<div class="flex text-white p-4">
			<div class="nav-item">
				<h1 class="font-bold text-2xl">Fashion store</h1>
			</div>
			<div class="nav-item">
				<ul class="nav-link-container">
					<li v-for="route in $router.getRoutes()">
						<router-link :to="route.path" class="text-white">
							{{ route.name }}
						</router-link>
					</li>
				</ul>
			</div>
			<div class="nav-item gap-x-2">
				<button class="icon-button">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						viewBox="0 0 20 20"
						fill="currentColor"
					>
						<path
							fill-rule="evenodd"
							d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
							clip-rule="evenodd"
						/>
					</svg>
				</button>
				<button class="icon-button">
					<svg
						xmlns="http://www.w3.org/2000/svg"
						class="h-5 w-5"
						viewBox="0 0 20 20"
						fill="currentColor"
					>
						<path
							d="M3 1a1 1 0 000 2h1.22l.305 1.222a.997.997 0 00.01.042l1.358 5.43-.893.892C3.74 11.846 4.632 14 6.414 14H15a1 1 0 000-2H6.414l1-1H14a1 1 0 00.894-.553l3-6A1 1 0 0017 3H6.28l-.31-1.243A1 1 0 005 1H3zM16 16.5a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zM6.5 18a1.5 1.5 0 100-3 1.5 1.5 0 000 3z"
						/>
					</svg>
				</button>
			</div>
		</div>
		<div class="flex flex-1 flex-col items-center justify-evenly">
			<h1 class="font-bold text-5xl">Välkommen</h1>
			<div class="flex gap-x-6">
				<Navcard bgcolor="#FF9C9C">Dam</Navcard>
				<Navcard bgcolor="#FFE455">Barn</Navcard>
				<Navcard bgcolor="#557CE0">Herr</Navcard>
				<Navcard bgcolor="#FFA36F">Baby</Navcard>
			</div>
		</div>
	</nav>
</template>

<script>
import Navcard from './Navcard.vue';
export default {
	name: 'Navbar',
	components: {
		Navcard,
	},
};
</script>

<style lang="scss" scoped>
nav {
	height: 20rem;
	&:before {
		@apply bg-[#E0556D] flex absolute w-full h-full;
		content: '';
		position: absolute;
		top: 0;
		width: 100%;
		height: 44%;
		z-index: -1;
		clip-path: polygon(0 0, 100% 0, 100% 50%, 0% 100%);
	}
	.nav-item {
		@apply flex w-full h-20 justify-center items-center;
		.nav-link-container {
			@apply flex gap-x-2;
			li {
				@apply inline-block relative px-2 capitalize;
				&:not(:last-child)::after {
					content: '';
					border: 1px solid white;
					background-color: white;
					border-width: 1px;
					position: absolute;
					right: -4px;
					top: 0;
					height: 100%;
				}
				.router-link-active {
					@apply font-bold;
				}
			}
		}
		.icon-button {
			@apply flex items-center justify-center;
			svg {
				@apply h-8 w-8;
			}
		}
	}
}
</style>
