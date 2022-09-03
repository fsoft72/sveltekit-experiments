<script lang="ts">
	import type { ColorTypes } from '$lib/utils/colors';

	export let title = '';
	export let subtitle = '';

	export let style = '';

	export let color: ColorTypes = 'is-primary';
</script>

<section class="hero {color}" {style}>
	<div class="hero-body">
		<p class="title">{title}</p>
		<p class="subtitle">{subtitle}</p>
	</div>
</section>
