<script>
	import ImageCard from '$lib/components/ImageCard.svelte';
	import Columns from '$lib/components/Columns.svelte';
	import Col from '$lib/components/Col.svelte';
	import Hero from '$lib/components/Hero.svelte';
</script>

<section class="section">
	<div class="container">
		<Hero
			title="SvelteKit"
			subtitle="A new way to build web applications"
			color="is-link"
			style="margin-bottom: 1rem; border-radius: 0.5rem"
		/>
		<Columns>
			<Col>
				<ImageCard
					image="https://bulma.io/images/placeholders/1280x960.png"
					userAvatarImage="https://bulma.io/images/placeholders/96x96.png"
					userName="John Smith"
					userTwitterHandle="@johnsmith"
					content="content here"
					postDate="2020-01-01"
				/>
			</Col>

			<Col shrink>
				<ImageCard
					image="https://bulma.io/images/placeholders/1280x960.png"
					userAvatarImage="https://bulma.io/images/placeholders/96x96.png"
					userName="John Smith"
					userTwitterHandle="@johnsmith"
					content="content here"
					postDate="2020-01-01"
					footerItems={[
						{ link: 'https://google.com', text: 'Google' },
						{ link: 'https://twitter.com', text: 'Twitter' },
						{ link: 'https://facebook.com', text: 'Facebook' }
					]}
				/>
			</Col>

			<Col>
				<ImageCard
					header="No image Card"
					userAvatarImage="https://bulma.io/images/placeholders/96x96.png"
					userName="John Smith"
					userTwitterHandle="@johnsmith"
					content="content here"
					postDate="2020-01-01"
				/>
			</Col>
		</Columns>
		<Columns>
			<Col>
				<ImageCard
					title="This is a great day to learn Svelte"
					subtitle="Subtitle here"
					footerItems={[
						{ link: 'https://google.com', text: 'Google' },
						{ link: 'https://twitter.com', text: 'Twitter' }
					]}
				/>
			</Col>

			<Col>
				<ImageCard
					header="Card header"
					title="This is a great day to learn Svelte"
					subtitle="Subtitle here"
					footerItems={[
						{ link: 'https://google.com', text: 'Google' },
						{ link: 'https://twitter.com', text: 'Twitter' }
					]}
				/>
			</Col>
		</Columns>
	</div>
</section>
