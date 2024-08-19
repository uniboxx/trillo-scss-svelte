<script lang="ts">
  import Header from './lib/Header.svelte';
  import Main from './lib/Main.svelte';
  import Sidebar from './lib/Sidebar.svelte';
</script>

<div class="container">
  <Header />
  <div class="content">
    <Sidebar />
    <Main />
  </div>
</div>

<style lang="scss">
  @use './styles/vars';

  .container {
    max-width: 120rem;
    margin: 8rem auto;
    background-color: var(--color-grey-light-1);
    box-shadow: var(--shadow-dark);

    // min-height: 50rem;

    @media only screen and (max-width: vars.$bp-largest) {
      margin: 0;
      max-width: 100%;
    }
  }

  .content {
    display: flex;

    @media only screen and (max-width: vars.$bp-medium) {
      flex-direction: column;
    }
  }
</style>
