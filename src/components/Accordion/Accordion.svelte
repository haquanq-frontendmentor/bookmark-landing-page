<script lang="ts">
  import { cn } from "../../utils/cn";
  import AccordionItem from "./AccordionItem.svelte";

  type AccordionProps = {
    data: Array<{ label: string; content: string }>;
    xClass?: string;
  };

  const { data, xClass }: AccordionProps = $props();
</script>

<ul class={cn("border-grey-300 w-full max-w-[33.875rem] border-b text-start", xClass)} role="list">
  {#each data as item, index}
    <AccordionItem {...item} {index} />
  {/each}
</ul>
