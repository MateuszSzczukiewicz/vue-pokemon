<template>
	<div class="card">
		<CardTop :card="card" />
		<img
			loading="lazy"
			class="card__img"
			:src="card.images.large"
			:alt="card.name"
		/>
		<CardBottom :card="card" />
	</div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import { type Card } from '@/types/cart.type';
import CardTop from '@/components/atoms/CardTop.vue';
import CardBottom from '@/components/atoms/CardBottom.vue';

export default defineComponent({
	name: 'BaseCard',
	components: {
		CardTop,
		CardBottom,
	},
	props: {
		card: {
			type: Object as PropType<Card>,
			required: true,
		},
	},
});
</script>
<style lang="scss" scoped>
.card {
	width: fit-content;

	&__img {
		width: 250px;
	}
}
</style>
