<script>
	export let d = 0;
	export let m = 0;

	export let shrink = false;

	$: {
		d = d || 6;
		m = m || d;
	}
</script>

<div class="column {shrink ? 'is-narrow' : ''}">
	<slot />
</div>
