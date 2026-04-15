<script>
	import Icon from 'svelte-awesome';
	import linkedinSquare from 'svelte-awesome/icons/linkedinSquare';
	import github from 'svelte-awesome/icons/github';
	let currentYear = new Date().getFullYear();
</script>

<footer class="w-full bg-slate-50 dark:bg-slate-950 py-12 px-6">
	<div class="flex flex-col items-center gap-4 w-full text-center max-w-7xl mx-auto">
		<div class="flex gap-10">
			<a
				href="#"
				class="text-slate-500 hover:text-slate-900 dark:hover:text-white underline underline-offset-4 font-body transition-all"
			>
				<div class="w-6 h-6">
					<Icon data={github} />
				</div>
			</a>
			<a
				href="#"
				class="text-slate-500 hover:text-slate-900 dark:hover:text-white underline underline-offset-4 font-body transition-all"
			>
				<div class="w-6 h-6">
					<Icon data={linkedinSquare} />
				</div>
			</a>
		</div>
		<p class="text-slate-900 dark:text-white font-headline font-medium text-sm">
			© {currentYear} Adrian Kulik
		</p>
	</div>
</footer>
