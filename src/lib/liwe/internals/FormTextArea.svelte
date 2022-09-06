<script lang="ts">
	// the name of the form creating the input
	// this is necessary for the aria attributes
	export let formName = 'form';

	export let label: string = '';
	export let name: string = '';
	export let value: string = '';
	export let required: boolean = false;

	export let status: '' | 'is-success' | 'is-warning' | 'is-danger' = '';

	export let message: string = '';
</script>

<div class="field">
	<label class="label" for="{formName}-{name}">{label}</label>
	<textarea id="{formName}-{name}" class="textarea" {name} {required}>{value}</textarea>
	<p class="help {status}">{message}</p>
</div>
