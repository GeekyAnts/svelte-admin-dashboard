<script>
  import colors from "./constant.js";
  export let segment;
  export let content;

  let isOnMouse = false;
</script>

<style>
  .selected {
    color: rgb(57, 187, 176);
  }
  a {
    text-decoration: none;
    display: flex;
    width: 100%;
    white-space: nowrap;
    padding: 0.5rem;
    align-items: "center";
  }
  a:hover {
    background: rgb(233, 233, 233);
  }
</style>

<ul class="p-5" style="background:{colors.primaryGray}">
  {#each content as list}
    <li class="p-1 text-gray-600 ">
      {#if list.title === 'Home'}
        <a class:selected={segment === undefined} href={list.route}>
          <i class="material-icons text-lg">{list.icon}</i>
          <span
            class="px-3 text-sm whitespace-no-wrap font-normal justify-center
            text-center">
            {list.title}
          </span>
        </a>
      {:else}
        <a class:selected={segment === list.route} href={list.route}>
          <i class="material-icons text-lg">{list.icon}</i>
          <span
            class="px-3 text-sm whitespace-no-wrap font-normal justify-center
            text-center">
            {list.title}
          </span>
        </a>
      {/if}
    </li>
  {/each}
</ul>
