<script lang="ts">
	// the name of the form creating the input
	// this is necessary for the aria attributes
	export let formName = 'form';

	export let label: string = '';
	export let name: string = '';
	export let value: string = '';
	export let required: boolean = false;

	export let options: Array<{ value: string; label: string }> = [];

	export let status: '' | 'is-success' | 'is-warning' | 'is-danger' = '';

	export let message: string = '';
</script>

<div class="field">
	<label class="label" for="{formName}-{name}">{label}</label>
	<div class="select">
		<select {name} {value} {required}>
			{#each options as option}
				<option value={option.value}>{option.label}</option>
			{/each}
		</select>
	</div>
	<p class="help {status}">{message}</p>
</div>
