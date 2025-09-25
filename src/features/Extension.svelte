<script lang="ts">
  import Paragraph from "../components/base/Paragraph.svelte";
  import Button from "../components/base/Button.svelte";

  import ChromeLogo from "../assets/images/logo-chrome.svg";
  import FirefoxLogo from "../assets/images/logo-firefox.svg";
  import OperaLogo from "../assets/images/logo-opera.svg";
  import Dots from "../assets/images/bg-dots.svg";
</script>

{#snippet ExtensionCard(label: string, description: string, logo: string)}
  <li class="w-70 rounded-lg pt-[2.6875rem] shadow-lg lg:nth-[2]:mt-10 lg:nth-[3]:mt-20">
    <img class="mx-auto mb-[2.125rem]" src={logo} alt="" />
    <h3 class="mb-[0.875rem] text-xl leading-none tracking-[0.01em]">{label}</h3>
    <p class="mb-[2.4375rem] text-[0.9375rem] leading-none">{description}</p>
    <img src={Dots} alt="" />
    <div class="p-6">
      <Button xClass="w-full" link="">Add & Install Extension</Button>
    </div>
  </li>
{/snippet}

<section class="flex flex-col items-center text-center">
  <h2 class="mb-[1.625rem] text-2xl leading-none md:text-[2rem]">Download the extension</h2>
  <Paragraph xClass="mb-[3.375rem] max-w-144">
    We’ve got more browsers in the pipeline. Please do let us know if you’ve got a favourite you’d like us to
    prioritize.
  </Paragraph>
  <ul
    class="flex flex-col gap-y-8 md:pl-1 md:*:nth-[2]:ml-[2.125rem] md:*:nth-[3]:ml-[2.3125rem] lg:flex-row lg:items-start"
  >
    {@render ExtensionCard("Add to Chrome", "Minimum version 62", ChromeLogo)}
    {@render ExtensionCard("Add to Firefox", "Minimum version 55", FirefoxLogo)}
    {@render ExtensionCard("Add to Opera", "Minimum version 46", OperaLogo)}
  </ul>
</section>
