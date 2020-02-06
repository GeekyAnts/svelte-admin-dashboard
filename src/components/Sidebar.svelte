<script>
  import { slide } from "svelte/transition";
  import { isSidebarVisible } from "./stores.js";

  import List from "./List.svelte";
  import colors from "./constant.js";

  export let segment;
  let isVisible = true;

  const unsubscribe = isSidebarVisible.subscribe(value => {
    isVisible = value;
  });

  let gray = colors.primaryGray;

  let userName = "Malinda Hollaway";
  let userEmail = "malinda-h@gmail.com";

  let sidebarLabels = [
    { route: ".", title: "Home", icon: "home" },
    { route: "typography", title: "Typography", icon: "format_underline" },
    { route: "tables", title: "Tables", icon: "view_list" },
    {
      route: "buttons",
      title: "Buttons",
      icon: "group_work"
    }
  ];
</script>

<style>
  nav {
    width: 260px;
    /* height: 100vh; */
    height: 100%;
    position: fixed;
    left: 0;
    top: 4em;
    font-weight: 300;
    padding: 10px;
    z-index: 300;
  }

  @media (max-width: 400px) {
    nav {
      width: 260px;
      height: 100%;
      position: fixed;
      left: 0;
      top: 4.5em;
      font-weight: 300;
      padding: 10px;
      z-index: 300;
    }
  }
</style>

{#if isVisible}
  <nav style="background-color:{colors.primaryGray}">
    <div class="flex flex-col pl-5">
      <div
        class="flex flex-row bg-gray-300 p-2 py-3 justify-center mt-5 rounded
        items-center hover:bg-gray-400"
        style="background-color:{colors.secondaryGray}">
        <div>
          <img
            src="https://byrushan.com/projects/material-admin/app/2.6.1/angular/assets/demo/img/profile-pics/8.jpg"
            alt="profile"
            height="35"
            width="35"
            class="rounded-full" />
        </div>
        <div class="flex flex-col ml-2">
          <p class="text-xs">{userName}</p>
          <p class="text-xs text-gray-500">{userEmail}</p>
        </div>
      </div>

    </div>
    <List content={sidebarLabels} {segment} />
  </nav>
{/if}
