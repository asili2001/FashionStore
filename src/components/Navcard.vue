<template>
	<button class="card">
		<div class="background"></div>
		<div class="z-10 absolute">
			<slot>Card</slot>
		</div>
	</button>
</template>

<script>
export default {
	name: 'Card',
	props: {
		bgcolor: {
			type: String,
			default: 'transparent',
		},
	},
};
</script>

<style lang="scss" scoped>
.card {
	@apply flex relative rounded-xl bg-white justify-center items-center font-bold text-2xl w-28 h-20 overflow-hidden;
	.background {
		@apply flex justify-center items-center rounded-xl w-full h-full;
		// do clip path like the bg but on the bottom
		background-color: v-bind(bgcolor);
		clip-path: polygon(0 70%, 101% 30%, 101% 100%, 0% 100%);
	}
}
</style>
