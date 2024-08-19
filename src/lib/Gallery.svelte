<script>
  import { base, icons } from '../js/constants';
</script>

<div class="gallery">
  <figure class="gallery__item">
    <img
      src={`${base}/img/hotel-1.jpg`}
      alt="Photo of hotel 1"
      class="gallery__photo" />
  </figure>
  <figure class="gallery__item">
    <img
      src={`${base}/img/hotel-2.jpg`}
      alt="Photo of hotel 2"
      class="gallery__photo" />
  </figure>
  <figure class="gallery__item">
    <img
      src={`${base}/img/hotel-3.jpg`}
      alt="Photo of hotel 3"
      class="gallery__photo" />
  </figure>
</div>

<style lang="scss">
  @use '../styles/vars';

  .gallery {
    display: flex;

    &__photo {
      width: 100%;
      display: block;
    }
  }
</style>
