<script context="module">
	import ProjectCard from '$lib/components/project-card.svelte';

  const projects =  [
		{
			name: "Kobe Sarausad",
			slug: "https://observablehq.com/d/f90eaa1c774a1b62",
			description: "test",
			image: "https://kobesar.github.io/images/profile.jpg"
		}
	];

  const authors = [
      {
        name: "Kobe Sarausad",
        intro: "test",
        picture: {
          url: "https://kobesar.github.io/images/profile.jpg"
        }
      }
    ];
</script>

<svelte:head>
	<title>My Portfolio project</title>
</svelte:head>

<h1 class="font-bold text-center mb-20 text-5xl">Welcome to my Portfolio</h1>

{#each authors as { name, intro, picture: { url } }}
	<div class="flex mb-40 items-end">
		<div class="mr-6">
			<h2 class="text-3xl mb-4 font-bold tracking-wider">{name}</h2>
			<p class="text-xl mb-4">{intro}</p>
		</div>

		<img class="mask mask-squircle h-48" src={url} alt={name} />
	</div>
{/each}

<div class="grid gap-10 md:grid-cols-4 md:px-10 lg:grid-cols-6 lg:-mx-52">
	{#each projects as { name, slug, description, image }}
		<ProjectCard {name} {description} url={image[0].url} {slug} />
	{/each}
</div>
