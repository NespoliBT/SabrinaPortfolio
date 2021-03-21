<script lang="ts">
  import { scale } from "svelte/transition";

  let presentationOpen = false;

  let n = 1;
  let slideNumber = 18;
  let storyDuration = 2000;

  function prevSlide() {
    if (n - 1 <= 0) {
      n = 1;
    } else {
      n -= 1;
    }
  }

  function nextSlide() {
    if (n + 1 > slideNumber) {
      presentationOpen = false;
      console.log(n);
    } else {
      n += 1;
    }
  }

  function closePresentation() {
    presentationOpen = false;
    n = 1;
  }
</script>

<div class="description">
  Lorem ipsum dolor, sit amet consectetur adipisicing elit. Autem tempora iure
  in, quos quia quidem quibusdam libero cupiditate? Esse incidunt a sed tenetur
  numquam ducimus aperiam provident iste dolores id.
  <div class="open" on:click={() => (presentationOpen = true)}>
    Sfoglia presentazione <span>廊</span>
  </div>
</div>

{#if presentationOpen}
  <div
    class="slides"
    in:scale={{ duration: 200 }}
    out:scale={{ duration: 200 }}
  >
    <div
      class="slide"
      on:mousedown={() => console.log("giu")}
      on:mouseup={() => console.log("su")}
    >
      <div class="exit" on:click={() => closePresentation()}>x</div>
      <div class="left" on:click={() => prevSlide()} />
      <div class="right" on:click={() => nextSlide()} />
      <div class="img">
        <div class="stories">
          {#each Array(slideNumber) as _, i}
            <div
              class={"story" + (n > i + 1 ? " watched" : "")}
              id={"story" + (i + 1)}
            />
          {/each}
        </div>
        <img
          src={"./img/ballosemitriste/BALLO SEMITRISTE SENZA INFO-" +
            n +
            ".jpg"}
          alt={n + ""}
        />
      </div>
    </div>
  </div>
{/if}

<style lang="scss">
  @import "./scss/slides.scss";
</style>
