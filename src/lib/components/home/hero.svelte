<script>
	import i18n from '$lib/i18n';
	import heroI18n from './hero.i18n';
	import BreakingNews from './news.svelte';
	import HeroAnimation from './hero-animation.svelte'
	import jQuery from 'jquery';

	export let lang;
	export let width;
	export let height;
  </script>

	{#if (width > 700)}
		<div id="large-header">
			<HeroAnimation />
		</div>
	{/if}
	<div class="hero">
		<div class="bg-overlay">
			<div class="content-wrapper">
					<div class="content">
						<picture>
							<source srcset="/images/hero/ag2-logo.webp" type="image/webp">
							<source srcset="/images/hero/ag2-logo.png" type="image/png"> 
							<img
								id="logo"
								height="128"
								width="111"
								src="/images/hero/ag2-logo.png"
								alt="Blackcoin Logo"
							/>
						  </picture>
						<h1>
							{i18n(heroI18n, 'blackcoin', lang)}
						</h1>
						<h2>{i18n(heroI18n, 'since2014', lang)}</h2>
						<a href="#community" class="join-community">
							<picture>
								<source srcset="/images/joincommunity.webp" type="image/webp">
								<source srcset="/images/joincommunity.png" type="image/png"> 
								<img
									id="cta"
									height="46"
									width="350"
									src="/images/joincommunity.png"
									alt="Join the Blackcoin Community!"
								/>
							  </picture>
						</a>
					</div>
					<br />
					<BreakingNews {lang} />
					<br />
				</div>
			</div>
	</div>

<style>
	.hero {
		background: url(/images/hero/tri.jpg);
		background-size: cover;
		background-position: 50%;
		background-attachment: fixed;
	}
	.hero .bg-overlay {
		background: rgba(17, 17, 17, 0.5);
		overflow: hidden;
		height: 100vh;
	}
	.hero .content-wrapper .content {
		text-align: center;
	}
	.hero {
		color: #ececec;
	}
	#logo {
		padding-top: 25%;
		width: 50%;
		height: auto;
	}
	#large-header {
		position: absolute;
		margin: o auto;
	}

	@media (min-width: 700px) {
		#logo {
			padding-top: 10%;
			width: 10%;
		}
	}
</style>
