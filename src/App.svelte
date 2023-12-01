<!-- App.svelte -->
<script>
  import Header from "./Header.svelte";
  import Content from "./Home.svelte";
  import Footer from "./Footer.svelte";
</script>
<main>
  <Header />
  <div class="content">
    <Content />
  </div>
  <Footer />
</main>

<style>
  .content {
    flex: 10;
    display: flex;
  }

  main {
    display: flex;
    flex-direction: column;
    height: 95vh;
  }
</style>
