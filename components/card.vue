<template>
	<div>
		<article class="uk-card uk-card-body uk-card-default uk-card-small">
			<p class="uk-badge">
				{{ rarity }}
			</p>
			<h3 class="uk-margin-remove-top">
				{{ name }}
			</h3>
			<p>
				{{ description }}
			</p>
		</article>
	</div>
</template>

<script>
	export default {
		props: {
			name: {
				type: String,
				required: false,
			},
			rarity: {
				type: String,
				required: true,
			},
			description: {
				type: String,
				required: true,
			},
		},
	}
</script>