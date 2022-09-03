<script lang="ts">
	interface FooterItem {
		link: string;
		text: string;
	}
	export let header = '';
	export let title = '';
	export let subtitle = '';
	export let image = '';
	export let userAvatarImage = '';
	export let userName = '';
	export let userTwitterHandle = '';
	export let content = '';
	export let postDate = '';

	export let footerItems: FooterItem[] = [];
</script>

<div class="card" style="max-width: min(400px,100%)">
	{#if header}
		<header class="card-header">
			<p class="card-header-title">{header}</p>
		</header>
	{/if}
	{#if image}
		<div class="card-image">
			<figure class="image is-4by3">
				<img src={image} alt="Placeholder" />
			</figure>
		</div>
	{/if}
	<div class="card-content">
		{#if title}
			<p class="title">{title}</p>
		{/if}
		{#if subtitle}
			<p class="subtitle">{subtitle}</p>
		{/if}
		<div class="media">
			{#if userAvatarImage}
				<div class="media-left">
					<figure class="image is-48x48">
						<img src={userAvatarImage} style="width: 48px; height: 48px" alt="User avatar" />
					</figure>
				</div>
			{/if}
			{#if userName || userTwitterHandle}
				<div class="media-content">
					<p class="title is-4">{userName}</p>
					<p class="subtitle is-6">{userTwitterHandle}</p>
				</div>
			{/if}
		</div>

		<div class="content">
			{@html content}
			{#if postDate}
				<br />
				<time datetime={postDate}>{postDate}</time>
			{/if}
		</div>

		{#if footerItems.length > 0}
			<footer class="card-footer">
				{#each footerItems as item}
					<a href={item.link} class="card-footer-item">{item.text}</a>
				{/each}
			</footer>
		{/if}
	</div>
</div>
