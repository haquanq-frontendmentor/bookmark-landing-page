<script lang="ts">
  import { setContext } from "svelte";

  const props = $props();

  let selectedTab = $state({ index: 0 });
  setContext("selected-tab", selectedTab);
</script>

<div class="flex w-full flex-col items-center">
  {@render props.children?.()}
</div>
