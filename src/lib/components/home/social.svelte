<script>
	import i18n from '$lib/i18n';
	import social from './social-links';
	import socialI18n from './social.i18n';
	export let lang;
</script>

<div class="container">
	<center>
		<h3>
			<a name="community" alt="Join the Blackcoin Community!">
				<span style="color: #FFFFFF;">{i18n(socialI18n, 'join_community', lang)}</span>
			</a>
		</h3>
	</center>
	<ul>
		{#each social as s}
			<li>
				<a href={s.url} target="_blank noreferer" rel="noopener">
					<picture>
					  <source srcset={s.img.split('.')[0]+".webp"} type="image/webp">
					  <source srcset={s.img} type="image/png">
					  <img height="102" width="125" src={s.img} alt={s.alt} />
					</picture>
				</a>
			</li>
		{/each}
	</ul>
</div>

<style>
	.container {
		overflow: hidden;
	}
	ul {
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;
	}
	li {
		width: 30%;
		margin: 1%;
	}

	@media (min-width: 700px) {
		li {
			width: 15%;
		}
	}
	@media (min-width: 1440px) {
		li {
			width: 5%;
		}
	}

</style>
