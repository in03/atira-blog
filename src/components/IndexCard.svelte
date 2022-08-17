<script>

	// href={item.slug} title={item.data.title} date={item.data.date}
	export let href = '#';

	/** @type {import('$lib/types').GHMetadata} */
	export let ghMetadata = null;
	export let title = 'Untitled post';
	/** @type {string} */
	export let stringData = 'no date';
	export let labels = []

</script>

<a
	sveltekit:prefetch
	class="w-full text-gray-900 hover:text-yellow-600 dark:text-gray-100 dark:hover:text-yellow-100"
	{href}
	><div class="mb-8 w-full">
		<div class="flex flex-col justify-between md:flex-row">
			<h4 class="mb-2 w-full flex-auto text-lg font-medium md:text-xl">
				{title}
			</h4>
			<div class="inline-flex flex-1 items-center">
				{#if ghMetadata && ghMetadata.reactions.total_count}
					<span
						class=" mr-2 min-w-[2rem] font-mono text-xs text-gray-700 text-opacity-70 dark:text-gray-300"
						>{ghMetadata.reactions.total_count} ♥</span
					>
				{/if}
				<p class="mb-4 w-32 text-left text-gray-500 md:mb-0 md:text-right">{stringData}</p>
			</div>
		</div>
		<div class="mb-2 justify-start">

			{#each labels as label}

				<!-- <span>{label.color}</span> -->
				<span class="text-xs mr-2 inline-block py-1 px-2.5 leading-none text-center whitespace-nowrap align-baseline 
							 font-bold outline outline-1 outline-gray-800 dark:outline-gray-300 rounded-full
							 text-gray-700 dark:text-gray-300"

					  style="background-color: hsla({ label.color[0]}, {label.color[1]}%, {label.color[2]}%, 50%); 
					  		 outline-color: hsl({ label.color [0]}, {label.color[1]}%, {label.color[2]}%); 
							 color: hsl({ label.color[0] }, { label.color[1] }%, { label.color[2]+20}%);">
					  {label.name}

				</span>

			{/each}

		</div>

		<p class="text-gray-600 dark:text-gray-400">
			<slot />
		</p>
	</div>
</a>

<style>
	span {
		/* color: hsl(rgba(255, 62, 0, var(--opacity)); */
	}
</style>
