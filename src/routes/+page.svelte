<script>
	import { projects } from '$lib/data/projects';
	import ProjectCard from '$lib/components/ProjectCard.svelte';
</script>

<!-- Hero Section -->
<section class="max-w-7xl mx-auto px-6 lg:px-12 mb-24">
	<div class="max-w-3xl">
		<!-- Typography: Label/Subtitle (Manrope, All caps, tertiary color) -->
		<p class="font-label uppercase tracking-[0.1em] text-sm text-tertiary mb-6">
			Frontend Developer & UI/UX Designer
		</p>

		<h1
			class="text-6xl md:text-8xl font-extrabold tracking-tighter text-on-background mb-8 leading-[0.95]"
		>
			Passionate about <span class="italic font-body font-light text-primary">meaningful</span> experiences on the web.
		</h1>
	</div>
</section>

<section class="max-w-7xl mx-auto px-6 lg:px-12">
	<div class="grid grid-cols-1 sm:grid-cols-2 gap-8">
		{#each projects as project (project)}
<ProjectCard
	title={project.title}
	tagline={project.tagline}
	imageUrl={project.imageUrl}
	imageUrl2={project.imageUrl2}
	imageUrl3={project.imageUrl3}
	mainTech={project.tech[0]}
	secondaryTech={project.tech.slice(1)}
/>
		{/each}
	</div>
</section>