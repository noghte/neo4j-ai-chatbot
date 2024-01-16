<script lang="ts">
	import { page } from '$app/stores';
	import ClearHistory from '$lib/components/ClearHistory.svelte';
	import LoginButton from '$lib/components/LoginButton.svelte';
	import Sidebar from '$lib/components/Sidebar.svelte';
	import SidebarFooter from '$lib/components/SidebarFooter.svelte';
	import SidebarList from '$lib/components/SidebarList.svelte';
	import ThemeToggle from '$lib/components/ThemeToggle.svelte';
	import UserMenu from '$lib/components/UserMenu.svelte';
	import { buttonVariants } from '$lib/components/ui/button';
	import { IconGitHub, IconSeparator, IconSvelteChat, IconVercel } from '$lib/components/ui/icons';
	import type { Chat } from '$lib/types';
	import { cn } from '$lib/utils';

	export let chats: Chat[];
</script>


<header class="flex justify-between items-center">

    <div class="flex-grow">
        {#if $page.data.session}
            <Sidebar>
                <SidebarList {chats} />
                <SidebarFooter>
                    <ThemeToggle />
                    <ClearHistory />
                </SidebarFooter>
            </Sidebar>
        {/if}
    </div>

    <h1 class="flex-grow-0 text-center">ProKinO AI chatbot</h1>

    <div class="flex-grow">
        {#if $page.data.session}
            <UserMenu />
        {:else}
            <div class="float-right">
                <LoginButton variant="link" showGithubIcon={false} text="Login" />
            </div>
        {/if}
    </div>

</header>
