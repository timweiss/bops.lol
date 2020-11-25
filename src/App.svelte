<script lang="ts">
	import type { Playlist } from './playlist';
	import playlists from '../assets/lists.json';

	let lists: Playlist[] = playlists;
</script>

<main>
	<h1>Explore Good Spotify Playlists</h1>
	<p>This is a highly opinionated list of playlists that you are free to extend with your own additions!</p>
	<p>Add <a href="https://github.com/timweiss/bops.lol">your own here</a> or send it in at <a href="mailto:playlists@bops.lol">playlists@bops.lol</a></p>

	<div class="playlists">
		{#each lists as playlist }
			<div class="item">
			<iframe title="Playlist from {playlist.user.name}" src="{playlist.url}" width="300" height="300" frameborder="0" allowtransparency="true" allow="encrypted-media"></iframe>
			<p class="author">from <a href="{playlist.user.url}">{playlist.user.name}</a></p>
			</div>
		{/each}
	</div>

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}

	h1 {
		color: #4ab7ff;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 700;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}

	@media (max-width: 640px) {
		iframe {
			max-width: 250px;
		}
	}

	.playlists .item {
		margin: 10px;
		display: inline-block;
	}
</style>