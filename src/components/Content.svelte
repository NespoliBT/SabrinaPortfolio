<script lang="ts">
  import Sidebar from "./Sidebar.svelte";
  import Contacts from "./Contacts.svelte";
  import About from "./About.svelte";

  import { Router, Route } from "svelte-routing";
</script>

<div class="content">
  <Sidebar />
  <Router>
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
