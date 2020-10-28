<script>
  import Nav from "./_components/Nav.svelte";

  export let segment;
</script>

<style>

</style>

<svelte:head>

  <meta name="viewport" content="width=device-width, initial-scale=0.5" />
</svelte:head>
<Nav {segment} />

<main class="section">
  <slot />
</main>
