<script lang="ts">
	import Columns from '$lib/components/Columns.svelte';
	import Col from '$lib/components/Col.svelte';
	import FormCreator from '$lib/liwe/FormCreator.svelte';

	const fields: any[] = [
		{
			name: 'login',
			label: 'Login',
			type: 'email'
		},
		{
			name: 'password',
			label: 'Password',
			type: 'password'
		}
	];
</script>

<section class="section">
	<div class="container">
		<Columns>
			<Col>
				<h1>FORM</h1>
				<FormCreator {fields} />
			</Col>
		</Columns>
	</div>
</section>
