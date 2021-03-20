<script lang="ts">
  import { fly } from "svelte/transition";
  import { onMount } from "svelte";

  let ready = false;
  onMount(() => (ready = true));
</script>

{#if ready}
  <div class="header" in:fly={{ x: -100 }}>
    <a href="/">
      <h1>
        Sabrina Nespoli <br />
        Portfolio
      </h1>
    </a>
  </div>
{/if}

<style lang="scss">
  @import "./scss/header.scss";
</style>
