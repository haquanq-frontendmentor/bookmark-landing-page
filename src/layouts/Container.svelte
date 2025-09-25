<script lang="ts">
  import type { Snippet } from "svelte";

  const { children }: { children: Snippet } = $props();
</script>

<div class="mx-auto w-[min(100vw-4rem,69.375rem)]">{@render children?.()}</div>
