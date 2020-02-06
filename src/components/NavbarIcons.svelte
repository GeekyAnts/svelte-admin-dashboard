<script>
  import { fade } from "svelte/transition";
  let scale = "1.7";
</script>

<style>
  .iconStyle {
    justify-content: flex-end;
    flex-direction: row;
    display: flex;
    text-align: center;
  }
  button {
    padding: 0px 12px;
  }
  button:hover {
    border-radius: 2px;
    background-color: rgb(97, 196, 187);
    transition: 0.5s;
  }
  button:focus {
    outline: 0;
  }
  i {
    font-size: 20px;
  }
</style>

<div class="container iconStyle align-center ">
  <button>
    <i class="material-icons">email</i>
  </button>
  <button>
    <i class="material-icons">notifications</i>
  </button>
  <button>
    <i class="material-icons">check_circle</i>
  </button>
  <button>
    <i class="material-icons">apps</i>
  </button>
  <button>
    <i class="material-icons">more_vert</i>
  </button>
</div>
