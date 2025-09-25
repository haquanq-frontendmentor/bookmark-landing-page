<script lang="ts">
  import { HeroIllustration } from "../assets/images";
  import Button from "../components/base/Button.svelte";
  import Paragraph from "../components/base/Paragraph.svelte";
  import Container from "../layouts/Container.svelte";
</script>

<section class="relative z-10">
  <div
    class="absolute top-[clamp(5.5rem,1.358rem+18.4091vw,15.625rem)] right-0 block h-[clamp(12.5rem,3.4351rem+38.6768vw,22rem)] w-3/4 rounded-l-full bg-blue-600 md:top-[12.375rem] md:w-[clamp(12.5rem,4.446rem+35.7955vw,32.1875rem)]"
  ></div>
  <Container>
    <div
      class="relative z-50 grid gap-x-8 gap-y-20 pt-[clamp(2rem,0.5091rem+6.3613vw,3.5625rem)] md:grid-flow-dense md:grid-cols-2"
    >
      <div class="hero-image-wrapper md:col-start-2">
        <img class="translate-x-[-0.3125rem] scale-110 md:max-w-[500%] md:scale-none" src={HeroIllustration} alt="" />
      </div>
      <div class="flex flex-col items-center text-center md:items-start md:text-start">
        <h1
          class="mb-[clamp(1.125rem,0.7672rem+1.5267vw,1.5rem)] text-[clamp(2rem,1.0458rem+4.0712vw,3rem)] leading-[clamp(2.5rem,1.7844rem+3.0534vw,3.25rem)] md:mt-20"
        >
          A Simple Bookmark Manager
        </h1>
        <Paragraph xClass="max-w-[31.25rem]">
          A clean and simple interface to organize your favourite websites. Open a new browser tab and see your sites
          load instantly. Try it for free.
        </Paragraph>
        <div class="mt-8 flex flex-wrap gap-4">
          <Button xClass="" link="">Get It on Chrome</Button>
          <Button link="" variant="secondary">Get It on Firefox</Button>
        </div>
      </div>
    </div>
  </Container>
</section>
