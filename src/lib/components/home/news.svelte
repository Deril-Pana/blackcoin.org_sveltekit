<script type="typescript">
	import newsI18n from './news.i18n';
	import news from './news';
	import i18n from '$lib/i18n';

	let i = 0;
	$: bn = news[i % news.length];

	setInterval(() => {
		i++;
	}, 5000);

	export let lang;
</script>

<br />
<div class="news-container">
	<br />
	<div class="newsBox">
		<div class="title">
			<h2>{i18n(newsI18n, 'latest_news', lang)}</h2>
		</div>
		<ul class="innerBox">
			<li>
				<h3>
					<a href={bn.url}>
						<span>{bn.date}</span>
						<span class="content">{i18n(bn, 'news', lang)}</span>
					</a>
				</h3>
			</li>
		</ul>
	</div>
	<br />
</div>
<br />

<style>
	* {
		margin: 0;
		padding: 0;
	}
	h2 {
		font-size: 15px;
		font-weight: 900;
		align-self: center;
	}
	h3 {
		font-size: 11px;
		font-weight: 300;
		padding: 5px 0 0 1rem;
	}
	.news-container {
		width: 100%;
		max-width: 960px;
		margin: 0 auto;
	}
	.newsBox {
		text-align: left;
		background: #151515;
		height: 40px;
		position: relative;
		border: solid 2px darkred;
		overflow: hidden;
	}
	.title {
		width: 20%;
		height: 100%;
		position: absolute;
		top: 0;
		background-color: red;
		display: grid;
		justify-items: center;
		align-itemjustify-items: center;
	}
	.innerBox {
		width: 80%;
		position: absolute;
		right: 0;
		top: 0;
	}
	.content {
		color: #ddb77a;
	}

	@media (min-width: 700px) {
		h2 {
			font-size: 20px;
		}
	}
	@media (min-width: 1080px) {
		h2 {
			font-size: 20px;
		}
		h3 {
			font-size: 20px;
			margin: 0px 0 10px 0;
			font-weight: 500;
		}
		.newsBox {
			height: 4rem;
		}
		.title {
			height: 4rem;
		}
		.title > h2 {
			line-height: 4rem;
		}
	}
	@media (max-aspect-ratio: 5/1) and (min-width: 2560px) {
		h3 {
			font-size: 20px;
			margin: 0px 0 10px 0;
			font-weight: 500;
		}
	}
</style>
