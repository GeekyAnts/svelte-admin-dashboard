<script>
  let value = 1;

  let leftState = false;
  let midState = false;
  let rightState = false;

  let radioStatus = "Nothing is selected";

  function toggle() {
    if (value === 0) {
      value = 1;
      return;
    }
    value = 0;
  }
</script>

<style>
  .caption {
    color: rgb(187, 184, 184);
    font-size: 14px;
    margin-top: 0.5rem;
  }

  .container {
    flex: 1;
    background-color: rgb(255, 255, 255);
    padding: 2rem;
    margin-top: 2rem;
    margin-bottom: 2rem;
    border-radius: 2px;
  }

  button:hover {
    background-color: rgb(11, 124, 213);
    cursor: default;
  }
  radio-button:hover {
    background-color: rgb(40, 158, 107);
  }

  .single-toggle {
    border-radius: 2px;
    background-color: rgb(34, 151, 240);
    color: white;
    padding: 10px;
    font-size: 13px;
  }

  .checked-button {
    background-color: rgb(34, 151, 240);
    color: white;
    padding: 12px;
    font-size: 13px;
  }
  .clicked {
    background-color: rgb(11, 124, 213);
  }
  .custom-clicked {
    color: white;
    background-color: rgb(0, 169, 244);
  }

  .rounded-left {
    border-bottom-left-radius: 2px;
    border-top-left-radius: 2px;
  }

  .rounded-right {
    border-bottom-right-radius: 2px;
    border-top-right-radius: 2px;
  }

  .sub-heading {
    font-size: 18px;
    margin-bottom: 2rem;
  }
  hr {
    display: block;
    margin-top: 1em;
    margin-bottom: 0.5em;
    margin-left: auto;
    margin-right: auto;
    border-style: inset;
    border-width: 0.5px;
    border-color: rgb(240, 240, 240);
  }
  .output {
    background-color: rgb(65, 65, 65);
    width: 100%;
    padding: 1rem;
    color: white;
    border-radius: 2px;
    font-size: 13px;
  }
  .main {
    color: rgb(142, 141, 141);
    margin-left: 30px;
  }
  .radiobtn {
    background-color: rgb(50, 199, 135);
  }
  .sub-container {
    margin-top: 5px;
  }
  .radioClicked {
    background-color: rgb(40, 158, 107);
  }
  .main-title {
    margin-bottom: 10px;
    font-weight: 300;
    color: rgb(94, 94, 94);
  }
  custom-button {
    color: rgb(87, 86, 86);
    padding: 12px;
    font-size: 13px;
    background-color: rgb(246, 246, 246);
    border: none;
    cursor: pointer;
  }
  subtitle {
    font-size: 14px;
    font-weight: 300;
  }
  button:focus {
    outline: 0;
  }
</style>

<svelte:head>
  <title>Buttons</title>
</svelte:head>

<div class="main">
  <h4 class="main-title">BUTTONS</h4>
  <subtitle>
    There are two directives that can make a group of buttons behave like a set
    of checkboxes, radio buttons, or a hybrfont-size:id where radio buttons can
    be unchecked.
  </subtitle>
</div>

<div class="container">
  <h3 class="sub-heading">Toggle States</h3>
  <button on:click={toggle} class="single-toggle" class:clicked={value === 1}>
    Single Toggle
  </button>
  <hr />
  <div class="output">{value}</div>
</div>
<div class="container">
  <h3 class="sub-heading">
    Checkbox
    <p class="caption">Checkbox-like buttons set with variable states</p>
  </h3>
  <div class="flex flex-row">
    <button
      class="checked-button rounded-left"
      class:clicked={leftState}
      on:click={() => (leftState = !leftState)}>
      Left
    </button>
    <button
      class="checked-button"
      class:clicked={midState}
      on:click={() => (midState = !midState)}>
      Middle
    </button>
    <button
      class="checked-button rounded-right"
      class:clicked={rightState}
      on:click={() => (rightState = !rightState)}>
      Right
    </button>
  </div>
  <hr />
  <div class="output">
    <p>{'{'}</p>
    <p>{`"left"` + ': ' + `${leftState} ,`}</p>
    <p>{`"middle"'` + ': ' + `${midState} ,`}</p>
    <p>{`"right"` + ': ' + `${rightState}`}</p>
    <p>{'}'}</p>

  </div>
</div>
<div class="container">
  <h3 class="sub-heading">
    Radio
    <p class="caption">
      Radio buttons with checked/unchecked states. Group can be created in two
      ways: using btnRadioGroup directive or using the same ngModel binding with
      several buttons (works only for template driven forms). Check the demo
      below for more info
    </p>
  </h3>
  <div class="flex flex-row">
    <button
      class="checked-button rounded-left"
      class:clicked={radioStatus === 'Left'}
      on:click={() => (radioStatus = 'Left')}>
      Left
    </button>
    <button
      class="checked-button"
      class:clicked={radioStatus === 'Middle'}
      on:click={() => (radioStatus = 'Middle')}>
      Middle
    </button>
    <button
      class="checked-button rounded-right"
      class:clicked={radioStatus === 'Right'}
      on:click={() => (radioStatus = 'Right')}>
      Right
    </button>
  </div>
  <div class="flex flex-row sub-container">
    <radio-button
      class="checked-button rounded-left radiobtn"
      class:radioClicked={radioStatus === 'Left'}
      on:click={() => (radioStatus = 'Left')}>
      Left
    </radio-button>
    <radio-button
      class="checked-button radiobtn"
      class:radioClicked={radioStatus === 'Middle'}
      on:click={() => (radioStatus = 'Middle')}>
      Middle
    </radio-button>
    <radio-button
      class="checked-button radiobtn rounded-right"
      class:radioClicked={radioStatus === 'Right'}
      on:click={() => (radioStatus = 'Right')}>
      Right
    </radio-button>
  </div>
  <hr />
  <div class="output">
    <p>{`"${radioStatus}"`}</p>
  </div>
</div>
<div class="container">
  <h3 class="sub-heading">
    Custom template styling
    <p class="caption">
      Use modifier class .btn-group--custom in order to get a template spefici
      styling on all button elements.
    </p>
  </h3>
  <div class="flex flex-row">
    <custom-button
      class="rounded-left"
      class:custom-clicked={leftState}
      on:click={() => (leftState = !leftState)}>
      Left
    </custom-button>
    <custom-button
      class:custom-clicked={midState}
      on:click={() => (midState = !midState)}>
      Middle
    </custom-button>
    <custom-button
      class="rounded-right"
      class:custom-clicked={rightState}
      on:click={() => (rightState = !rightState)}>
      Right
    </custom-button>
  </div>
  <div class="flex flex-row sub-container">
    <custom-button
      class="checked-custom-button rounded-left"
      class:custom-clicked={radioStatus === 'Left'}
      on:click={() => (radioStatus = 'Left')}>
      Left
    </custom-button>
    <custom-button
      class="checked-custom-button"
      class:custom-clicked={radioStatus === 'Middle'}
      on:click={() => (radioStatus = 'Middle')}>
      Middle
    </custom-button>
    <custom-button
      class="checked-custom-button rounded-right"
      class:custom-clicked={radioStatus === 'Right'}
      on:click={() => (radioStatus = 'Right')}>
      Right
    </custom-button>
  </div>
</div>
