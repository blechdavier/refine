<script lang="ts">
	import ProjectPreview from '$lib/ProjectPreview.svelte';

	/*
    export const load: PageServerLoad = async ({ locals }) => {
        const session = await locals.auth.validate();
        if (!session) throw redirect(302, '/login');
        return {
            userId: session.user.userId,
            username: session.user.username
        };
    };
    */
	// load user data from this

	export let data;
	console.log(data);
</script>

<nav
	class="h-12 flex items-center justify-between backdrop-blur shadow-sm bg-gradient-to-br from-white/30 to-white/20"
>
	<a class="flex items-center" href="/">
		<div class="bg-black rounded-sm shadow-lg w-8 h-8 mx-2 overflow-hidden">
			<div class="bg-amber-400 h-2 w-12 -rotate-45 translate-y-4" />
			<div class="bg-gray-400 h-2 w-12 -rotate-45 translate-y-4" />
			<div class="bg-amber-700 h-2 w-12 -rotate-45 translate-y-4" />
		</div>
		<h1 class="inline-block font-bold text-xl">Refine</h1>
	</a>
	<div class="flex items-center text-lg font-bold gap-x-2 px-2">
		{#if data}
			<p>Hi, {data.username}!</p>
			<a href="/logout" class="text-lg font-bold text-black hover:text-gray-900">Log Out</a>
		{:else}
			<a href="/login" class="text-lg font-bold text-black hover:text-gray-900">Log In</a>
			<a href="/signup" class="px-4 py-1 text-white bg-black rounded-md shadow-md hover:bg-gray-900"
				>Get Refine free</a
			>
		{/if}
	</div>
</nav>
{#if data}
	<h1 class="m-4 text-5xl font-bold text-black">Welcome back, {data.username}!</h1>
	<h2 class="m-4 text-2xl font-bold text-black">Latest Project</h2>
	<div class="m-4">
		<ProjectPreview
			projectName="Refine"
			projectImage="/refine.png"
			projectId="uuid-12312312-sdasd-12-31-23-12-31-23-1whatever"
			projectDescription="A project management and productivity software, submitted to the Maine App Challenge."
		/>
	</div>
	<h2 class="m-4 text-2xl font-bold text-black">All Projects</h2>
	<div class="flex space-x-4 h-full m-4">
		<ProjectPreview
			projectName="Rust Minecraft Server"
			projectImage="https://www.firework.gg/lobby.png"
			projectId="uuid-12312312-sdasd-12-31-23-12-31-23-1whatever"
			projectDescription="An implementation of the Minecraft server application from the ground up. With the framework that we will create with our server application, we will reimplement the Glide and Battle minigames from Minecraft: Console Edition."
		/><ProjectPreview
			projectName="Earthful"
			projectImage="https://images.unsplash.com/photo-1421789665209-c9b2a435e3dc?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTV8fGVhcnRofGVufDB8fDB8fHww&auto=format&fit=crop&w=500&q=60"
			projectId="uuid-12312312-sdasd-12-31-23-12-31-23-1whatever"
			projectDescription="A web app that allows users to visualize marine debris location and frequency."
		/><ProjectPreview
			projectName="Snowed In"
			projectImage="https://images.unsplash.com/photo-1483921020237-2ff51e8e4b22?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=500&q=60"
			projectId="uuid-12312312-sdasd-12-31-23-12-31-23-1whatever"
			projectDescription="Online multiplayer tile-based building game using socket.io and TypeScript."
		/>
	</div>
{:else}
	<div class="flex flex-col items-center justify-center h-[calc(100vh-64px)]">
		<h1 class="text-6xl font-bold text-black">What is Refine?</h1>
		<p class=" mt-4 text-2xl text-black font-bold max-w-xl text-center">
			Refine is the project design and management tool built on simplicity and efficiency.
		</p>
		<a
			href="/signup"
			class="mt-8 px-4 py-2 text-lg font-bold text-white bg-black rounded-md shadow-md hover:bg-gray-900"
			>Get Refine free</a
		>
	</div>
{/if}
