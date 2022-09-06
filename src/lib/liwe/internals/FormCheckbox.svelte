<script lang="ts">
	// the name of the form creating the input
	// this is necessary for the aria attributes
	export let formName = 'form';

	export let label: string = '';
	export let name: string = '';
	export let value: string = '';
	export let required: boolean = false;
	export let checked: boolean = false;

	export let status: '' | 'is-success' | 'is-warning' | 'is-danger' = '';

	export let message: string = '';
</script>

<div class="field">
	<label class="checkbox" style="user-select: none;" for="{formName}-{name}">
		<input id="{formName}-{name}" type="checkbox" {value} {checked} {required} />
		&nbsp; {label}
	</label>
	<p class="help {status}">{message}</p>
</div>
