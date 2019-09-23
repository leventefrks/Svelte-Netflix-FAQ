<script>
  import Button from "./Button.svelte";

  const buttonText = "try 30 days free";
  const title = "Frequently asked questions";

  const items = [
    {
      id: 0,
      title: "What is Netflix?",
      content:
        "Netflix is a streaming service that offers a wide variety of award-winning TV shows, movies, anime, documentaries, and more on thousands of internet-connected devices. You can watch as much as you want, whenever you want without a single commercial – all for one low monthly price. There's always something new to discover and new TV shows and movies are added every week!"
    },
    {
      id: 1,
      title: "How much does Netflix cost?",
      content:
        "Watch Netflix on your smartphone, tablet, Smart TV, laptop, or streaming device, all for one low fixed monthly fee. Plans start from 2 490 Ft a month. No extra costs or contracts."
    },
    {
      id: 2,
      title: "Where can I watch?",
      content:
        "Watch anywhere, anytime, on an unlimited number of devices. Sign in with your Netflix account to watch instantly on the web at netflix.com from your personal computer or on any internet connected device that offers the Netflix app, including smart TVs, smartphones, tablets, streaming media players and game consoles. You can also download your favorite shows with the iOS, Android, or Windows 10 app. Use downloads to watch while you're on the go and without an internet connection. Take Netflix with you anywhere."
    },
    {
      id: 3,
      title: "How do I cancel?",
      content:
        "Netflix is flexible. There are no pesky contracts and no commitments. You can easily cancel your account online in two clicks. There are no cancellation fees – start or stop your account anytime."
    },
    {
      id: 4,
      title: "What can I watch on Netflix?",
      content:
        "Netflix has an extensive library of feature films, documentaries, TV shows, anime, award-winning Netflix originals, and more. Watch as much as you want, anytime you want. Join free for 30 days to see everything Netflix has to offer."
    },
    {
      id: 5,
      title: "How does this free trial work?",
      content:
        "Try us free for 30 days! If you enjoy your Netflix trial, do nothing and your membership will automatically continue for as long as you choose to remain a member. Cancel anytime before your trial ends and you won’t be charged. There’s no complicated contract, no cancellation fees, and no commitment. Cancel online anytime, 24 hours a day."
    }
  ];

  let openAccordionId = null;
  let isAccordionOpen = false;

  export const handleClick = currentId => {
    if (openAccordionId === currentId) {
      isAccordionOpen = !isAccordionOpen;
    } else {
      openAccordionId = currentId;
      isAccordionOpen = true;
    }
  };
</script>

<style type="text/sass">
  :global(body) {
    margin: 0;
    width: 100vw;
    height: 100vh;
    background: #000;
  }

  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 900px;
    text-align: left;
    color: #fff;
    font-family: Helvetica, Arial, Sans-Serif;
  }

  h1 {
    margin: 0;
    padding: 1rem 0 2rem;
    text-align: center;
  }

  .faq-list {
    width: 75%;
    margin: 2em auto;
    list-style-type: none;
  }

  .faq-list-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.8em 2.2em 0.8em 1.2em;
    margin: 0.5rem 0 1px 0;
    background: #303030;
    font-size: 1.6rem;
    overflow: hidden;
  }

  .faq-list-item-icon {
    fill: #fff;
    font-size: 1.5rem;
    width: 1em;
    height: 1em;
    transform: rotate(-45deg);
  }

  .faq-list-item-icon-open {
    transform: rotate(0deg);
  }

  .accordion {
    display: none;
    padding: 31px;
    margin-bottom: 5px;
    background-color: #303030;
  }

  .accordion-open {
    display: block;
    font-size: 1.6rem;
  }
</style>

<main>
	<h1>{title}</h1>
  <ul class="faq-list">
    	{#each items as { id, title, content }, i (id)}
      <li
        on:click={() => handleClick(id)}
        id={id}
        class="faq-list-item"
      >
        <span>{title}</span>
          <svg
            class="faq-list-item-icon"
            class:faq-list-item-icon-open={openAccordionId === id && isAccordionOpen}
          >
            <path d="M10.5 9.3L1.8.5.5 1.8l8.8 8.7-8.8 8.8 1.3 1.2 8.7-8.7 8.8 8.7 1.2-1.2-8.7-8.8 8.7-8.7L19.3.5l-8.8 8.8z">
            </path>
          </svg>
      </li>
      <div class="accordion" class:accordion-open="{openAccordionId === id && isAccordionOpen}">{content}</div>
     {/each}
  </ul>
  <Button text={buttonText}/>
</main>