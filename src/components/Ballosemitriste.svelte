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
      n = 1;
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
  <span>BALLO SEMITRISTE</span> nasce contestualmente al corso “Marketing
  Management e Comunicazione della Musica” presso Scuola di Produzione Artistica
  (Milano). <br />
  Il progetto si propone di essere un esercizio nel campo dell’organizzazione di
  eventi a tutto tondo: tocca sia aree logistiche che tecniche, oltre che grafiche
  e di comunicazione. Per questo motivo, si tratta di un progetto che non ha ancora
  avuto applicazione concreta, ma che spera di diventare realtà in un futuro non
  troppo lontano. <br />
  L’obiettivo che mi son posta personalmente è stato elaborare un evento al quale
  io per prima avrei voluto partecipare, dai colori pop e dallo sguardo nostalgico.
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
