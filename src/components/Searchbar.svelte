<script>
  let searchText = "Search for people, files, documents...";
  let isFocused = null;
  let isBlur = null;
  $: myIcon = isFocused ? "arrow_back" : "search";
  let inputValue = "";
  inputValue = isBlur ? "" : inputValue;

  const inputHandler = event => {
    inputValue = event.target.value;
  };
  const blurHandler = event => {
    isFocused = false;
    inputValue = "";
  };
</script>

<style>
  .search-bar {
    background: rgba(176, 237, 223, 0.3);
    margin: 0 20px;
    width: 60%;
    border-radius: 3px;
    font-size: 14px;
  }
  .serach-bar-bg {
    background: white;
  }
  input:focus {
    outline: 0;
  }
  input:focus::placeholder {
    color: rgb(79, 78, 78);
  }
  input::placeholder {
    color: white;
    font-weight: "bold";
  }
  .focused-icon {
    transition-duration: 300ms;
    transform: rotate(360deg);
    color: rgb(79, 78, 78);
  }
  .blurred-icon {
    transition-duration: 300ms;
    transform: rotate(0deg);
    color: white;
  }
  @media (min-width: 1024px) {
    .search-bar {
      background-color: rgb(160, 224, 233);
      font-size: 12px;
    }
  }
</style>

<div
  class="w-1/2 mx-auto search-bar font-light text-white px-5 py-2 flex flex-row"
  class:serach-bar-bg={isFocused}>
  <i
    class="material-icons m-auto mx-1"
    class:focused-icon={isFocused}
    class:blurred-icon={!isFocused && isFocused !== null}
    style="font-size:20px">
    {myIcon}
  </i>
  <input
    type="text"
    class="container bg-transparent pl-1 text-gray-500"
    placeholder={searchText}
    value={inputValue}
    on:input={inputHandler}
    on:focus={() => (isFocused = true)}
    on:blur={blurHandler} />
</div>
