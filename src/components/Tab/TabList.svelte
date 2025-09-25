<script lang="ts">
  const props = $props();
</script>

<div class="border-grey-300 grid w-full max-w-[45.5625rem] border-b md:grid-cols-3" role="tablist" data-tablist>
  {@render props.children?.()}
</div>
