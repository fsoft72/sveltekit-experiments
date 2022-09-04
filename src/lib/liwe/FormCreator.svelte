<script lang="ts">
	import FormInput from './internals/FormInput.svelte';

	export let fields: any[] = [];

	export let submitLabel: string = 'Submit';

	// the form name is an unique id for the page (used by A11y)
	let name: string = 'formXXX';

	// the form reference
	let _form: any = null;

	$: {
		console.log('FIELDS: ', fields);
	}

	const internalOnSubmit = (e: Event) => {
		e.preventDefault();
		e.stopImmediatePropagation();
		e.stopPropagation();
		console.log('SUBMIT', _form);

		// put form fields data into a JSON object
		const data: Record<string, any> = {};
		for (const field of fields) {
			data[field.name] = _form[field.name].value;
		}

		console.log('=== DATA: ', data);
	};
</script>

<form bind:this={_form} id={name} class="form" on:submit={internalOnSubmit} method="post">
	{#each fields as field}
		<FormInput formName={name} {...field} />
	{/each}

	<div class="field">
		<div class="control">
			<button class="button is-link">{submitLabel}</button>
		</div>
	</div>
</form>
