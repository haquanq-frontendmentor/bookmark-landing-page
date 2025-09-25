<script lang="ts">
  import { getContext, type Snippet } from "svelte";

  interface TabButtonProps {
    index: number;
    children?: Snippet;
  }
  const selectedTab = getContext("selected-tab") as { index: number };

  const handleClick = () => {
    selectedTab.index = props.index;
  };

  const selected = () => props.index === selectedTab.index;

  const props: TabButtonProps = $props();
</script>

<button
  class="border-grey-300 group relative border-t py-[1.1875rem] text-[1.0625rem] leading-none text-blue-950 transition-colors hover:text-red-400 md:border-none md:pt-0 md:pb-[1.9375rem]"
  type="button"
  role="tab"
  class:active={selected()}
  onclick={handleClick}
  aria-selected={selected()}
  aria-controls={`tabpanel-${props.index}`}
  data-tabbutton
>
  <span
    class="absolute bottom-0 left-1/2 block h-1 w-1/2 -translate-x-1/2 bg-red-400 opacity-0 transition-opacity duration-300 group-aria-selected:opacity-100 md:w-full"
  >
  </span>
  <span>
    {@render props.children?.()}
  </span>
</button>
