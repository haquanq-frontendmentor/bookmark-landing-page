<script lang="ts">
  import type { Snippet } from "svelte";
  import { cn } from "../../utils/cn";

  type ParagraphProps = {
    xClass?: string;
    children?: Snippet;
  };

  const { children, xClass, ...restProps }: ParagraphProps = $props();
</script>

<p class={cn("text-base, text-grey-500 leading-6 md:text-lg md:leading-7", xClass)} {...restProps}>
  {@render children?.()}
</p>
