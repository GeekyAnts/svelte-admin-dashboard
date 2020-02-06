<script>
  import Searchbar from "./Searchbar.svelte";
  import NavbarIcons from "./NavbarIcons.svelte";
  import { isSidebarVisible } from "./stores.js";

  import colors from "../components/constant.js";

  let title = "Material Admin 2.0";
  let isVisible = false;
  let width;

  $: if (width <= 1279 && isVisible === false) {
    isSidebarVisible.update(value => (value = false));
  } else if (width > 1279) {
    isSidebarVisible.update(value => (value = true));
  }

  function showSidebar() {
    isSidebarVisible.update(value => (value = !value));
  }
</script>

<style>
  .heading {
    font-size: 17px;
    margin: 9px 10px 9px 20px;
    align-self: center;
    justify-content: flex-start;
    overflow-wrap: normal;
    width: 20rem;
  }
  .top-bar {
    height: 4rem;
  }
  .menu {
    margin-left: 2rem;
  }

  button:focus {
    outline: 0;
  }
</style>

<svelte:window bind:innerWidth={width} />

<div
  class="fixed left-0 top-0 right-0 text-white px-1 py-3 z-30 shadow-sm flex
  flex-row h-1/5 top-bar"
  style="background:{colors.primary}">
  {#if width <= 1279}
    <button class="menu" on:click={showSidebar}>
      <i class="material-icons">menu</i>
    </button>
  {/if}
  {#if width >= 648}
    <h3 class="heading font-normal">{title}</h3>
  {/if}
  <!-- <Searchbar /> -->
  <NavbarIcons />
</div>
