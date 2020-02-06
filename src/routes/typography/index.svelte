<script>
  let bodyData =
    "Pellentesque lacinia sagittis libero et feugiat. Etiam volutpat adipiscing tortor non luctus. Vivamus venenatis vitae metus et aliquet. Praesent vitae justo purus. In hendrerit lorem nisl, ac lacinia urna aliquet non. Quisque nisi tellus, rhoncus quis est sit amet, lacinia euismod nunc. Aenean nec nibh velit. Fusce quis ante in nisl molestie fringilla. Nunc vitae ante id magna feugiat condimentum. Maecenas sit amet urna massa. Integer eu lectus sollicitudin, hendrerit est ac, sollicitudin nisl. Quisque viverra sodales lectus nec ultrices. Fusce elit dolor, dignissim a nunc id, varius suscipit turpis. Cras porttitor turpis vitae leo accumsan molestie. Morbi vitae luctus leo. Sed nec scelerisque magna, et adipiscing est. Proin lobortis lectus eu sem ullamcorper, commodo malesuada quam fringilla. Curabitur ac nunc dui. Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Fusce sagittis enim eu est lacinia, ut egestas ligula imperdiet.";
</script>

<style>
  .caption {
    color: rgb(187, 184, 184);
    font-size: 13px;
    margin: 0.5rem 0 1.5rem 0;
  }
  .main {
    color: rgb(142, 141, 141);
    margin-left: 30px;
  }
  .main-title {
    margin-bottom: 10px;
    font-weight: 300;
    color: rgb(94, 94, 94);
  }
  .container {
    flex: 1;
    background-color: rgb(255, 255, 255);
    padding: 2rem;
    margin-top: 2rem;
    margin-bottom: 2rem;
    border-radius: 2px;
  }
  .sub-heading {
    margin-bottom: 2rem;
  }
  .bodyContent {
    color: rgb(116, 122, 128);
    font-size: 13px;
  }
  .content-line {
    color: rgb(116, 122, 128);
    margin-bottom: 2rem;
    font-size: 14px;
  }
  .highlighted {
    color: rgb(255, 133, 174);
  }
  ul {
    list-style: disc;
    margin: 0 2rem 3rem;
    color: rgb(116, 122, 128);
  }
  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    margin-bottom: 1.5rem;
  }

  h1 {
    font-size: 2em;
  }
  h2 {
    font-size: 1.75em;
  }
  h3 {
    font-size: 1.5em;
  }
  h4 {
    font-size: 1.25em;
  }
  h5 {
    font-size: 1em;
  }
  h6 {
    font-size: 0.5em;
  }

  .list-container {
    justify-content: space-between;
  }

  li {
    font-size: 14px;
  }
  .unstyled-list {
    list-style: none;
    margin: 0;
    margin-bottom: 2rem;
  }
  .nested-list {
    list-style: circle;
    margin-bottom: 0;
  }
  @media screen and (max-width: 640px) {
    .list-container {
      justify-content: space-between;
      flex: 1;
      flex-direction: column;
    }
  }
</style>

<svelte:head>
  <title>Typography</title>
</svelte:head>

<div class="main">
  <h4 class="main-title">TYPOGRAPHY</h4>
</div>

<div class="container">
  <h4 class="sub-heading">Body Copy</h4>
  <p class="bodyContent">{bodyData}</p>
</div>

<div class="container">
  <h4 class="sub-heading">
    Headings
    <p class="caption">
      All HTML headings,
      <span class="highlighted">{'<h1>'}</span>
      through
      <span class="highlighted">{'<h6>'}</span>
      , are available.
    </p>
    <p class="content-line">
      <span class="highlighted">.h1</span>
      through
      <span class="highlighted">.h6</span>
      classes are also available, for when you want to match the font styling of
      a heading but cannot use the associated HTML element.
    </p>
  </h4>
  <h1>h1. Svelte heading</h1>
  <h2>h2. Svelte heading</h2>
  <h3>h3. Svelte heading</h3>
  <h4>h4. Svelte heading</h4>
  <h5>h5. Svelte heading</h5>
  <h6>h6. Svelte heading</h6>
</div>

<div class="container">
  <h4 class="sub-heading">
    Lists
    <p class="caption">
      All lists
      <span class="highlighted">{' —<ul>'}</span>
      ,
      <span class="highlighted">{'<ol>'}</span>
      and
      <span class="highlighted">{'<dl>—'}</span>
      have their margin-top removed and a
      <span class="highlighted">{'margin-bottom: 1rem'}</span>
      . Nested lists have no margin-bottom.
    </p>
  </h4>
  <h5 class="mb-2">Custom styled</h5>
  <p class="content-line">
    Use below given custom list style classes style the bullets.
  </p>
  <div class="flex flex-row text-sm list-container">
    <ul>
      <li>Lorem ipsum dolor sit amet</li>
      <li>Consectetur adipiscing elit</li>
      <li>Integer molestie lorem at massa</li>
      <li>Facilisis in pretium nisl aliquet</li>
      <li>Nulla volutpat aliquam velit</li>
      <li>Faucibus porta lacus fringilla vel</li>
      <li>Aenean sit amet erat nunc</li>
      <li>Eget porttitor lorem</li>
    </ul>
    <ul>
      <li>Lorem ipsum dolor sit amet</li>
      <li>Consectetur adipiscing elit</li>
      <li>Integer molestie lorem at massa</li>
      <li>Facilisis in pretium nisl aliquet</li>
      <li>Nulla volutpat aliquam velit</li>
      <li>Faucibus porta lacus fringilla vel</li>
      <li>Aenean sit amet erat nunc</li>
      <li>Eget porttitor lorem</li>
    </ul>
    <ul>
      <li>Lorem ipsum dolor sit amet</li>
      <li>Consectetur adipiscing elit</li>
      <li>Integer molestie lorem at massa</li>
      <li>Facilisis in pretium nisl aliquet</li>
      <li>Nulla volutpat aliquam velit</li>
      <li>Faucibus porta lacus fringilla vel</li>
      <li>Aenean sit amet erat nunc</li>
      <li>Eget porttitor lorem</li>
    </ul>
  </div>
  <hr class="mb-5" />

  <h5 class="mt-5">Unstyled</h5>
  <p class="content-line">
    Remove the default
    <span class="highlighted">{'list-style'}</span>
    and left margin on list items (immediate children only). This only applies
    to immediate children list items, meaning you will need to add the class for
    any nested lists as well.
  </p>
  <ul class="unstyled-list">
    <li>Lorem ipsum dolor sit amet</li>
    <li>Consectetur adipiscing elit</li>
    <li>Integer molestie lorem at massa</li>
    <li>Facilisis in pretium nisl aliquet</li>
    <li>
      Nulla volutpat aliquam velit
      <ul class="nested-list">
        <li>Phasellus iaculis neque</li>
        <li>Purus sodales ultricies</li>
        <li>Vestibulum laoreet porttitor sem</li>
        <li>Ac tristique libero volutpat at</li>
      </ul>
    </li>
    <li>Faucibus porta lacus fringilla vel</li>
    <li>Aenean sit amet erat nunc</li>
    <li>Eget porttitor lorem</li>
  </ul>
</div>
