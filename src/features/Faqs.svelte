<script lang="ts">
  import Paragraph from "../components/base/Paragraph.svelte";
  import Accordion from "../components/Accordion/Accordion.svelte";
  import Button from "../components/base/Button.svelte";

  const faqs: { question: string; answer: string }[] = [
    {
      question: "What is Bookmark?",
      answer:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tincidunt justo eget ultricies fringilla. Phasellus blandit ipsum quis quam ornare mattis.",
    },
    {
      question: "How can I request a new browser?",
      answer:
        "Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet. Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdie tVivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet.",
    },
    {
      question: "Is there a mobile app?",
      answer:
        "Sed consectetur quam id neque fermentum accumsan. Praesent luctus vestibulum dolor, ut condimentum urna vulputate eget. Cras in ligula quis est pharetra mattis sit amet pharetra purus. Sed sollicitudin ex et ultricies bibendum.",
    },
    {
      question: "What about other Chromium browsers?",
      answer:
        "Integer condimentum ipsum id imperdiet finibus. Vivamus in placerat mi, at euismod dui. Aliquam vitae neque eget nisl gravida pellentesque non ut velit.",
    },
  ];
</script>

<section
  class="mt-[clamp(8.75rem,7.6169rem+4.8346vw,9.9375rem)] mb-[clamp(7.75rem,6.1994rem+6.6158vw,9.375rem)] flex flex-col items-center text-center"
>
  <h2 class="mb-[1.625rem] text-2xl leading-8 md:text-[2rem]">Frequently Asked Questions</h2>
  <Paragraph xClass="mb-14 max-w-[31.25rem]">
    Here are some of our FAQs. If you have any other questions you’d like answered please feel free to email us.
  </Paragraph>
  <Accordion xClass="mb-[3.375rem]" data={faqs.map((v) => ({ label: v.question, content: v.answer }))} />
  <Button link="">More Info</Button>
</section>
