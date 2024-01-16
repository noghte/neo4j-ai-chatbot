<script lang="ts">
	import ExternalLink from '$lib/components/ExternalLink.svelte';
	import { cn } from '$lib/utils';

	let className: string | undefined | null = undefined;
	export { className as class };
</script>

<p
	class={cn('px-2 text-center text-xs leading-normal text-muted-foreground', className)}
	{...$$restProps}
>
	Developed at
	<ExternalLink href="http://esbg.bmb.uga.edu/">ESBG lab</ExternalLink> at 
	<ExternalLink href="https://uga.edu">the University of Georgia</ExternalLink>
	.
</p>
