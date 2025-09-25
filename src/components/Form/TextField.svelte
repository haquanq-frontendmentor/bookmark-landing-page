<script lang="ts">
  import type { Attachment } from "svelte/attachments";
  import { cn } from "../../utils/cn";

  interface TextFieldProps {
    name: string;
    label: string;
    placeholder?: string;
    required?: boolean;
    xClass?: string;
  }

  const props: TextFieldProps = $props();

  let errorMessage = $state("");

  const inputId = props.name + "-input";
  const inputHintId = props.name + "-input-hint";

  const inputAttachment: Attachment<HTMLInputElement> = (input) => {
    const validate = () => {
      if (input.validity.valueMissing) errorMessage = "Whoops, can't be empty";
      else if (input.validity.typeMismatch) errorMessage = "Whoops, make sure it's an email";
      else errorMessage = "";
      input.setAttribute("aria-invalid", String(!input.validity.valid));
    };

    input.addEventListener("blur", () => {
      validate();
    });

    input.addEventListener("invalid", () => {
      validate();
    });
  };
</script>

<div class={cn("rounded-sm ", errorMessage !== "" && "bg-red-400", props.xClass)}>
  <label class="sr-only" for={inputId}>{props.label}</label>
  <input
    class="placeholder:text-grey-500 relative z-10 h-12 w-full rounded-sm border-2 border-transparent bg-white px-[1.375rem] text-sm tracking-wide aria-[invalid=true]:border-red-400"
    id={inputId}
    type="email"
    placeholder={props.placeholder}
    required={props.required}
    aria-invalid="false"
    aria-describedby={inputHintId}
    {@attach inputAttachment}
  />
  <span
    class="text-grey-50 block w-full rounded-sm pt-1 pb-[0.375rem] pl-3 text-start text-xs italic"
    hidden={errorMessage === ""}
    id={inputHintId}>{errorMessage}</span
  >
</div>
