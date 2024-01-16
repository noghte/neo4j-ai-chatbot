<script lang="ts">
	import ExternalLink from '$lib/components/ExternalLink.svelte';
	import { Button } from '$lib/components/ui/button';
	import { IconArrowRight } from '$lib/components/ui/icons';
	import type { UseChatHelpers } from 'ai/svelte/dist';

	export let input: UseChatHelpers['input'];

	const exampleMessages = [
		{
			heading: 'Show some proteins that have mutations',
			message: `Show 10 proteins that have mutations`
		},
		{
			heading: 'All proteins having "EGFR" in their uniprot names',
			message: 'List the proteins that have EGFR in the hasUniprotPrimaryName property'
		},
		{
			heading: 'What are some EGFR\'s mutations?',
			message: `What are some EGFR\'s mutations?`
		}
	];
</script>

<div class="mx-auto max-w-2xl px-4">
	<div class="rounded-lg border bg-background p-8">
		<h1 class="mb-2 text-lg font-semibold">Welcome to ProKinO AI Chatbot!</h1>
		<p class="mb-2 leading-normal text-muted-foreground">
			This is an AI chatbot built for 
			<ExternalLink href="https://prokino.uga.edu">ProKinO</ExternalLink> at
			the University of Georgia's <ExternalLink href="http://esbg.bmb.uga.edu/">ESBG</ExternalLink>
			.
		</p>
		<p class="leading-normal text-muted-foreground">
			You can start a conversation here or try the following examples:
		</p>
		<div class="mt-4 flex flex-col items-start space-y-2">
			{#each exampleMessages as message}
				<Button
					variant="link"
					class="h-auto p-0 text-base"
					on:click={() => ($input = message.message)}
				>
					<IconArrowRight class="mr-2 text-muted-foreground" />
					{message.heading}
				</Button>
			{/each}
		</div>
	</div>
</div>
