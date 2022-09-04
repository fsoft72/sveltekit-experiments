<script lang="ts">
	// the name of the form creating the input
	// this is necessary for the aria attributes
	export let formName = 'form';

	export let type: 'text' | 'select' | 'checkbox' | 'radio' | 'textarea' | 'email' | 'password' = 'text';
	export let label: string = '';
	export let name: string = '';
	export let placeholder: string = '';
	export let value: string = '';

	export let status: '' | 'is-success' | 'is-warning' | 'is-danger' = '';

	export let message: string = '';

	export let iconLeft: string = '';

	let iconRight: string = '';
	let hasIconsLeft: boolean = false;
	let hasIconsRight: boolean = false;

	let showButton: boolean = false;

	let _field: HTMLInputElement;

	const _focus = (e: Event) => {
		const target = e.target as HTMLInputElement;

		if (type === 'password') showButton = true;
	};

	const _blur = (e: Event) => {
		if (type === 'password') showButton = false;
	};

	const _button = (e: Event) => {
		const target = _field;

		console.log('==== BUTTON: ', target);

		if (target.type === 'password') {
			target.type = 'text';
		} else {
			target.type = 'password';
		}
	};

	$: {
		console.log('=== NAME: ', name, type, status);

		switch (status) {
			case 'is-danger':
				iconRight = 'fa-exclamation-triangle';
				break;
			case 'is-success':
				iconRight = 'fa-check';
				break;
		}

		switch (type) {
			case 'email':
				iconLeft = 'fa-envelope';
				break;
			case 'password':
				iconLeft = 'fa-lock';
				break;
		}

		if (iconRight) hasIconsRight = true;
		if (iconLeft) hasIconsLeft = true;
	}
</script>

<div class="field">
	<label class="label" for="{formName}-{name}">{label}</label>
	<div class="control {hasIconsLeft ? 'has-icons-left' : ''} {hasIconsRight || showButton ? 'has-icons-right' : ''}">
		<input bind:this={_field} on:focus={_focus} id="{formName}-{name}" class="input {status}" {name} {type} {placeholder} {value} />
		{#if iconLeft}
			<span class="icon is-small is-left">
				<i class="fas {iconLeft}" />
			</span>
		{/if}

		{#if iconRight}
			<span class="icon is-small is-right">
				<i class="fas {iconRight}" />
			</span>
		{/if}
	</div>
	{#if showButton}
		<div class="icon is-small is-right" on:click={_button} style="z-index: 1000">
			<i class="fas fa-eye" />
		</div>
	{/if}
	<p class="help {status}">{message}</p>
</div>
