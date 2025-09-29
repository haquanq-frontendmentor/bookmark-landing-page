<script lang="ts">
  import type { Snippet } from "svelte";
  import type { HTMLButtonAttributes } from "svelte/elements";
  import { cn } from "../../utils/cn";
  interface ButtonProps {
    children: Snippet;
    link?: string;
    variant?: "primary" | "secondary" | "accent";
    type?: HTMLButtonAttributes["type"];
    xClass?: string;
  }

  const { children, link, variant = "primary", type = "button", xClass, ...restProps }: ButtonProps = $props();

  const baseClass = cn(
    "font-medium cursor-pointer shadow-lg text-sm py-[0.9375rem] px-[1.375rem] rounded-sm border-2 leading-none border-transparent hover:bg-white transition-colors block text-center tracking-[0.02em]",
    {
      "bg-blue-600 text-grey-50 hover:text-blue-600 hover:border-blue-600": variant === "primary",
      "bg-grey-50 text-grey-500 hover:text-grey-500 hover:border-grey-500": variant === "secondary",
      "bg-red-400 text-grey-50 hover:text-red-400 hover:border-red-400": variant === "accent",
    },
  );
</script>

{#if link !== undefined}
  <a href={link} {...restProps} class={cn(baseClass, xClass)}>
    {@render children?.()}
  </a>
{:else}
  <button {type} {...restProps} class={cn(baseClass, xClass)}>
    {@render children?.()}
  </button>
{/if}
