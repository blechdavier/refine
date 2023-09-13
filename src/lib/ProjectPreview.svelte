<script lang="ts">
	export let projectName: string;
	export let projectDescription: string;
	export let projectImage: string | undefined;
	export let projectId: string;
	let color = [
		'red-400',
		'yellow-300',
		'green-400',
		'teal-500',
		'blue-400',
		'indigo-400',
		'purple-500'
	][projectName.length % 7];
</script>

<div class="w-96 shadow-lg backdrop-blur rounded-lg bg-white overflow-hidden">
	<div class="bg-{color} h-2 w-full" />
	<h3 class="m-4 text-2xl font-bold text-black">{projectName}</h3>
	<img src={projectImage} alt="" class="w-full h-48 object-cover" />
	<p class="m-4 text-black line-clamp-2">{projectDescription}</p>
</div>
