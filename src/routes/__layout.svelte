<script context="module">
  export const load = async ({ page }) => ({
    props: {
      key: page.path,
    },
  });
</script>

<script>
  import "../app.css";
  // import Nav from "$lib/Nav.svelte";
  import Footer from "$lib/Footer.svelte";
  import PageTransition from "$lib/PageTransition.svelte";
  export let key;
</script>

<div
  class="bg-gray-100 flex flex-col min-h-screen font-ptsans selection:bg-blueGray-200"
>
  <!-- <Nav /> -->
  <main class="flex-grow w-full">
    <PageTransition refresh={key}>
      <slot />
    </PageTransition>
  </main>
  <Footer class="flex-shrink-0" />
</div>
