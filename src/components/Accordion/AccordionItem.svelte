<script lang="ts">
  import type { Attachment } from "svelte/attachments";
  import { slide } from "svelte/transition";

  interface AccordionItemProps {
    label: string;
    content: string;
    index: number;
  }

  let showingContent = $state(false);

  const accordionButtonAttachment: Attachment<HTMLButtonElement> = (button) => {
    button.addEventListener("click", () => {
      const expanded = button.getAttribute("aria-expanded") === "true";
      button.setAttribute("aria-expanded", String(!expanded));
      showingContent = !expanded;
    });
  };

  const props: AccordionItemProps = $props();
</script>

<li class="accordion-item [&:nth-child(2)_button]:pb-[1.625rem]">
  <h3 class="block text-base leading-none font-normal tracking-[-0.03em] md:text-lg md:tracking-[0em]">
    <button
      class="border-grey-300 group flex w-full items-center justify-between border-t pt-[1.625rem] pr-6 pb-5 transition-colors hover:text-red-400"
      type="button"
      aria-expanded="false"
      aria-controls={"accordion-content-" + props.index}
      class:active={showingContent}
      {@attach accordionButtonAttachment}
    >
      <span>{props.label}</span>
      <svg
        class="transition-transform group-aria-expanded:rotate-180"
        xmlns="http://www.w3.org/2000/svg"
        width="18"
        height="12"
      >
        <path
          class="stroke-blue-600 transition-colors group-aria-expanded:stroke-red-400"
          fill="none"
          stroke-width="3"
          d="M1 1l8 8 8-8"
        />
      </svg>
    </button>
  </h3>
  <div id={"accordion-content-" + props.index}>
    {#if showingContent}
      <div class="text-grey-500 overflow-hidden text-base leading-9" transition:slide>
        <div class="h-[1.25rem]"></div>
        <p>{props.content}</p>
        <div class="h-[1.875rem]"></div>
      </div>
    {/if}
  </div>
</li>
