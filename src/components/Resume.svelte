<script lang="ts">
  import { scale } from "svelte/transition";

  import { onMount } from "svelte";

  let ready = false;
  onMount(() => (ready = true));
</script>

{#if ready}
  <div class="resumeCurriculum" in:scale={{ duration: 500 }}>
    <div class="download">Download <span></span></div>
    <img src="./img/Résumé Sabrina Nespoli-1.jpg" alt="" />
  </div>
{/if}

<style lang="scss">
  @import "./scss/resumeCurriculum.scss";
</style>
