<script lang="ts">
	import type { PageData } from './$houdini';

	export let data: PageData;

	$: ({ EpisodeRange } = data);
	$: episodes = $EpisodeRange.data?.allEpisode ?? [];
</script>

<ul role="list">
	{#each episodes as item}
		<li>
			<a
				class="block p-4 m-5 border border-solid border-stone-400 rounded-md hover:bg-sky-700 hover:cursor-pointer hover:no-underline"
				href="/episodes/{item.episodeNumber}"
			>
				<p class="m-0">{item.episodeNumber}</p>
                <p>{item.question}</p>
			</a>
		</li>
	{/each}
</ul>
