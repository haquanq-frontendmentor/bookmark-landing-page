<script lang="ts">
  import { getContext, type Snippet } from "svelte";

  interface TabPanelProps {
    index: number;
    children?: Snippet;
  }

  const props: TabPanelProps = $props();

  const selectedTab = getContext("selected-tab") as { index: number };
</script>

<div
  id={`tabpanel-${props.index}`}
  role="tabpanel"
  aria-labelledby={`tab-${props.index}`}
  hidden={selectedTab.index !== props.index}
>
  {@render props.children?.()}
</div>
