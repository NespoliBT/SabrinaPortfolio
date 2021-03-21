<script lang="ts">
  import Sidebar from "./Sidebar.svelte";
  import Ballosemitriste from "./Ballosemitriste.svelte";
  import Contacts from "./Contacts.svelte";
  import Resume from "./Resume.svelte";
  import Curriculum from "./Curriculum.svelte";
  import About from "./About.svelte";

  import { Router, Route } from "svelte-routing";
</script>

<div class="content">
  <Sidebar />
  <Router>
    <Route path="ballosemitriste">
      <Ballosemitriste />
    </Route>
    <Route path="curriculum">
      <Curriculum />
    </Route>
    <Route path="resume">
      <Resume />
    </Route>
    <Route path="contacts">
      <Contacts />
    </Route>
    <Route path="/">
      <About />
    </Route>
  </Router>
</div>

<style lang="scss">
  @import "./scss/content.scss";
</style>
