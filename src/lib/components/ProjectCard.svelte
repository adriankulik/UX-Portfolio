<script lang="ts">
	const {
		title,
		tagline,
		imageUrl,
		imageUrl2,
		imageUrl3,
		mainTech,
		secondaryTech = [],
		class: className = ''
	} = $props<{
		title: string;
		tagline: string;
		imageUrl: string;
		imageUrl2?: string;
		imageUrl3?: string;
		mainTech: string;
		secondaryTech?: string[];
		class?: string;
	}>();

	const images = [imageUrl, imageUrl2, imageUrl3].filter(
		(img): img is string => typeof img === 'string'
	);

	const count = images.length;

	const isSingle = count === 1;
	const isTwo = count === 2;
	const isMany = count >= 3;
</script>

<div class={`h-full flex flex-col ${className}`}>
	<div
		class="rounded-3xl overflow-hidden relative transition-all duration-500 hover:shadow-xl aspect-square bg-surface-container-low"
	>
		{#if isSingle}
			<div class="overflow-hidden w-full h-full">
				<img
					src={images[0]}
					alt={title}
					class="w-full h-full object-cover transition-transform duration-500 ease-out cursor-pointer"
				/>
			</div>
		{:else if isTwo}
			<div class="grid grid-cols-2 w-full h-full gap-1">
				<div class="overflow-hidden">
					<img
						src={images[0]}
						alt={title}
						class="w-full h-full object-cover transition-transform duration-500 ease-out cursor-pointer"
					/>
				</div>

				<div class="overflow-hidden">
					<img
						src={images[1]}
						alt={title}
						class="w-full h-full object-cover transition-transform duration-500 ease-out cursor-pointer"
					/>
				</div>
			</div>
		{:else if isMany}
			<div class="grid grid-cols-2 grid-rows-2 gap-1 w-full h-full">
				<div class="col-span-2 row-span-1 overflow-hidden">
					<img
						src={images[0]}
						alt={title}
						class="w-full h-full object-cover transition-transform duration-500 ease-out cursor-pointer"
					/>
				</div>

				<div class="overflow-hidden">
					<img
						src={images[1]}
						alt={title}
						class="w-full h-full object-cover transition-transform duration-500 ease-out cursor-pointer"
					/>
				</div>

				<div class="overflow-hidden">
					<img
						src={images[2]}
						alt={title}
						class="w-full h-full object-cover transition-transform duration-500 ease-out cursor-pointer"
					/>
				</div>
			</div>
		{/if}

		<div
			class="absolute inset-0 bg-gradient-to-t from-on-background/40 to-transparent opacity-0 hover:opacity-100 transition-opacity duration-500"
		/>
	</div>

	<div class="mt-6 pl-2 flex-1 flex flex-col">
		<div class="flex gap-2 mb-3 flex-wrap">
			<span
				class="bg-surface-container-high px-3 py-1 rounded-full text-xs uppercase tracking-widest text-on-surface-variant"
			>
				{mainTech}
			</span>

			{#each secondaryTech as tech (tech)}
				<span
					class="bg-surface-container-high px-3 py-1 rounded-full text-xs uppercase tracking-widest text-on-surface-variant"
				>
					{tech}
				</span>
			{/each}
		</div>

		<h3 class="text-2xl font-bold mb-2">{title}</h3>
		<p class="text-on-surface-variant">{tagline}</p>
	</div>
</div>
