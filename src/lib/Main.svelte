<script>
  import { base, icons } from '../js/constants';
  import Cta from '../layouts/Cta.svelte';
  import Details from '../layouts/Details.svelte';
  import Gallery from '../layouts/Gallery.svelte';
  import Overview from '../layouts/Overview.svelte';
</script>

<main class="hotel-view">
  <Gallery />
  <Overview />
  <Details />
  <Cta />
</main>

<style lang="scss">
  @use '../styles/vars';

  .hotel-view {
    // height: 80rem; //! DA RIMUOVERE
    background-color: #fff;
  }
</style>
