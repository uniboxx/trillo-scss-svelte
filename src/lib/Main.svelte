<script>
  import { base, icons } from '../js/constants';
  import Cta from './Cta.svelte';
  import Details from './Details.svelte';
  import Gallery from './Gallery.svelte';
  import Overview from './Overview.svelte';
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
