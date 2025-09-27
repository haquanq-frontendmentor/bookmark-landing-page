<script lang="ts">
  import { Tab1Illustration, Tab2Illustration, Tab3Illustration } from "../assets/images";
  import Button from "../components/base/Button.svelte";
  import Paragraph from "../components/base/Paragraph.svelte";
  import { Tab, TabButton, TabList, TabPanel } from "../components/Tab";
</script>

{#snippet FeatureItem(label: string, description: string, image: string)}
  <div
    class="grid min-h-127 gap-x-[clamp(5rem,-3.4375rem+17.5781vw,7.8125rem)] gap-y-20 pt-18 md:grid-cols-[1fr_min(100%,27.8125rem)]"
  >
    <div class="relative flex items-start justify-center md:justify-end">
      <span
        class="absolute right-[clamp(2rem,-2.0553rem+17.3028vw,6.25rem)] bottom-[clamp(-4rem,-0.0916rem+-8.1425vw,-2rem)] -left-80 block h-[90%] rounded-r-full bg-blue-600 md:right-[4.125rem] md:bottom-0 md:h-88"
      ></span>
      <img class="z-10 md:max-w-[500%]" src={image} alt="" />
    </div>
    <section class="flex flex-col items-center md:items-start md:pt-[4.125rem] md:text-start">
      <h3
        class="mb-[clamp(0.875rem,0.0997rem+3.3079vw,1.6875rem)] text-[clamp(1.5rem,1.0229rem+2.0356vw,2rem)] leading-none"
      >
        {label}
      </h3>
      <Paragraph xClass="mb-8">{description}</Paragraph>
      <Button>More Info</Button>
    </section>
  </div>
{/snippet}

<section class="relative flex flex-col items-center py-[9.375rem] text-center md:pt-[7.4375rem] md:pb-[9.875rem]">
  <h2 class="mb-[clamp(0.875rem,0.1594rem+3.0534vw,1.625rem)] text-2xl leading-none md:text-[2rem]">Features</h2>
  <Paragraph xClass="mb-[clamp(2.5rem,1.6818rem+3.6364vw,4.5rem)] max-w-[34.375rem]">
    Our aim is to make it quick and easy for you to access your favourite websites. Your bookmarks sync between your
    devices so you can access them on the go.
  </Paragraph>

  <Tab>
    <TabList>
      <TabButton index={0}>Simple Bookmarking</TabButton>
      <TabButton index={1}>Speedy Searching</TabButton>
      <TabButton index={2}>Easy Sharing</TabButton>
    </TabList>
    <TabPanel index={0}>
      {@render FeatureItem(
        "Bookmark in one click",
        "Organize your bookmarks however you like. Our simple drag-and-drop interface gives you complete control over how you manage your favourite sites.",
        Tab1Illustration,
      )}
    </TabPanel>
    <TabPanel index={1}>
      {@render FeatureItem(
        "Intelligent search",
        "Our powerful search feature will help you find saved sites in no time at all. No need to trawl through all of your bookmarks.",
        Tab2Illustration,
      )}
    </TabPanel>
    <TabPanel index={2}>
      {@render FeatureItem(
        "Share your bookmarks",
        "Easily share your bookmarks and collections with others. Create a shareable link that you can send at the click of a button.",
        Tab3Illustration,
      )}
    </TabPanel>
  </Tab>
</section>
