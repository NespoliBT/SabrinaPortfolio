<script lang="ts">
  import { scale } from "svelte/transition";
  const links = [
    {
      link: "/burgerking",
      name: "Burger King",
    },
    {
      link: "/humanavintage",
      name: "Humana Vintage",
    },
    {
      link: "/ballosemitriste",
      name: "Ballo Semitriste",
    },
    {
      link: "/curriculum",
      name: "Curriculum Vitae",
    },
    {
      link: "/resume",
      name: "Résumé",
    },
    {
      link: "/contacts",
      name: "Contatti",
    },
  ];
</script>

<ul class="sidebar">
  <!-- <a href="/burgerking"><li>Burger King</li></a>
  <a href="/humanavintage"><li>Humana Vintage</li></a>
  <a href="/ballosemitriste"><li>Ballo Semitriste</li></a>
  <a href="/curriculum"><li>Curriculum Vitae</li></a>
  <a href="/resume"><li>Résumé</li></a>
  <a href="/contacts"><li>Contatti</li></a> -->
  {#each links as l, i}
    <a href={l.link}>
      <li style={`animation-delay:${(i + 1) * 0.1}s;`}>{l.name}</li>
    </a>
  {/each}
</ul>

<style lang="scss">
  @import "./scss/sidebar.scss";
</style>
