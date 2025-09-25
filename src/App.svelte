<script lang="ts">
  import Container from "./layouts/Container.svelte";
  import Extension from "./features/Extension.svelte";
  import Faqs from "./features/Faqs.svelte";
  import ContactUs from "./features/ContactUs.svelte";
  import Footer from "./features/Footer.svelte";
  import Nav from "./features/Nav.svelte";
  import Intro from "./features/Intro.svelte";
  import Features from "./features/Features.svelte";
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
