<script>
  import { base, icons } from '../js/constants';
</script>

<div class="overview">
  <h1 class="overview__heading">Hotel Las Palmas</h1>
  <div class="overview__stars">
    <svg class="overview__icon-star">
      <use xlink:href={`${icons}#icon-star`}></use>
    </svg>
    <svg class="overview__icon-star">
      <use xlink:href={`${icons}#icon-star`}></use>
    </svg>
    <svg class="overview__icon-star">
      <use xlink:href={`${icons}#icon-star`}></use>
    </svg>
    <svg class="overview__icon-star">
      <use xlink:href={`${icons}#icon-star`}></use>
    </svg>
    <svg class="overview__icon-star">
      <use xlink:href={`${icons}#icon-star`}></use>
    </svg>
  </div>
  <div class="overview__location">
    <svg class="overview__icon-location">
      <use xlink:href={`${icons}#icon-location-pin`}></use>
    </svg>
    <button class="btn-inline">Albuferia, Portugal</button>
  </div>

  <div class="overview__rating">
    <div class="overview__rating-average">8.6</div>
    <div class="overview__rating-count">429 votes</div>
  </div>
</div>

<style lang="scss">
  @use '../styles/vars';

  .overview {
    display: flex;
    border-bottom: var(--line);
    align-items: center;

    &__heading {
      font-size: 2.25rem;
      font-weight: 300;
      text-transform: uppercase;
      letter-spacing: 1px;
      padding: 1.5rem 3rem;

      @media only screen and (max-width: vars.$bp-small) {
        font-size: 1.8rem;
        padding: 1.25rem 2rem;
      }

      @media only screen and (max-width: vars.$bp-smallest) {
        font-size: 1.3rem;
        padding: 1.25rem 1rem;
        padding-left: 0.5rem;
        text-align: center;
      }
    }

    &__stars {
      margin-right: auto;
      display: flex;
    }

    &__icon-star,
    &__icon-location {
      width: 1.75rem;
      height: 1.75rem;
      fill: var(--color-primary);

      @media only screen and (max-width: vars.$bp-smallest) {
        width: 1.3rem;
        height: 1.3rem;
      }
    }

    &__icon-location {
      margin-right: 0.5rem;
    }

    &__location {
      font-size: 1.2rem;
      display: flex;
      align-items: center;
      margin-right: 3rem;

      @media only screen and (max-width: vars.$bp-smallest) {
        margin-right: 1rem;
      }
    }

    &__rating {
      background-color: var(--color-primary);
      color: #fff;
      padding: 0 2.25rem;
      align-self: stretch;

      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      @media only screen and (max-width: vars.$bp-small) {
        padding: 0 1.5rem;
      }

      &-average {
        font-size: 2.25rem;
        font-weight: 300;
        margin-bottom: -3px;

        @media only screen and (max-width: vars.$bp-small) {
          font-size: 1.8rem;
        }
      }

      &-count {
        font-size: 1.2rem;
        text-transform: uppercase;

        @media only screen and (max-width: vars.$bp-small) {
          font-size: 0.8rem;
          text-align: center;
        }
      }
    }
  }
</style>
