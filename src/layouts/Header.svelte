<script>
  import { base } from '../js/constants';
  import Nav from '../lib/Header-Nav.svelte';
  import SearchForm from '../lib/SearchForm.svelte';
</script>

<header class="header">
  <img src={`${base}/img/logo.png`} alt="trillo logo" class="logo" />
  <SearchForm />
  <Nav />
</header>

<style lang="scss">
  @use '../styles/vars';
  .header {
    font-size: 1.4rem;
    height: 7rem;
    background-color: #fff;
    border-bottom: var(--line);

    display: flex;
    justify-content: space-between;
    align-items: center;

    @media only screen and (max-width: vars.$bp-xsmall) {
      flex-wrap: wrap;
      height: 11rem;
      align-content: space-around;
    }
  }
  .logo {
    height: 3.25rem;
    margin-left: 2rem;
  }
</style>
