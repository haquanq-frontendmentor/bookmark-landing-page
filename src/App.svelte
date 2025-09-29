<script lang="ts">
  import Container from "./layouts/Container.svelte";
  import Extension from "./components/Extension.svelte";
  import Faqs from "./components/Faqs.svelte";
  import ContactUs from "./components/ContactUs.svelte";
  import Footer from "./components/Footer.svelte";
  import Nav from "./components/Nav.svelte";
  import Intro from "./components/Intro.svelte";
  import Features from "./components/Features.svelte";
</script>

<header>
  <Nav />
</header>
<main>
  <Intro />
  <Container>
    <Features />
    <Extension />
    <Faqs />
  </Container>
</main>
<aside>
  <ContactUs />
</aside>
<Footer />
