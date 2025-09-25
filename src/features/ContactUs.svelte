<script lang="ts">
  import type { Attachment } from "svelte/attachments";
  import Button from "../components/base/Button.svelte";
  import TextField from "../components/Form/TextField.svelte";

  const formAttachment: Attachment<HTMLFormElement> = (form) => {
    form.addEventListener("submit", (e) => {
      form.checkValidity();
      e.preventDefault();
    });
  };
</script>

<section
  class="text-grey-50 flex flex-col items-center justify-center bg-blue-600 px-8 pt-[4.4375rem] pb-[4.625rem] text-center [--focus-outline-color:var(--color-white)]"
>
  <p class="mb-[2.375rem] ml-[0.1875rem] text-[0.8125rem] leading-none tracking-[0.4em] uppercase">
    35.000+ already joined
  </p>
  <h2 class="text-grey-50 mb-[2.25rem] max-w-120 text-[2rem] leading-10">Stay up-to-date with what we're doing</h2>
  <form class="flex w-[min(100%,27.625rem)] flex-wrap items-start gap-4" novalidate {@attach formAttachment}>
    <TextField
      xClass="min-w-60 grow-[999]"
      label="Email address"
      name="email"
      placeholder="Enter your email address"
      required
    />
    <Button xClass="grow " variant="accent" type="submit">Contact Us</Button>
  </form>
</section>
