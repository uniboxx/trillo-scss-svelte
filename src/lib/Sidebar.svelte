<script>
  import { icons } from '../js/constants';
</script>

<nav class="sidebar">
  <ul class="side-nav">
    <li class="side-nav__item side-nav__item--active">
      <a href="#" class="side-nav__link">
        <svg class="side-nav__icon">
          <use xlink:href={`${icons}#icon-home`}></use>
        </svg>
        <span>Hotel</span>
      </a>
    </li>
    <li class="side-nav__item">
      <a href="#" class="side-nav__link">
        <svg class="side-nav__icon">
          <use xlink:href={`${icons}#icon-aircraft-take-off`}></use>
        </svg>
        <span>Flight</span>
      </a>
    </li>
    <li class="side-nav__item">
      <a href="#" class="side-nav__link">
        <svg class="side-nav__icon">
          <use xlink:href={`${icons}#icon-key`}></use>
        </svg>
        <span>Car rental</span>
      </a>
    </li>
    <li class="side-nav__item">
      <a href="#" class="side-nav__link">
        <svg class="side-nav__icon">
          <use xlink:href={`${icons}#icon-map`}></use>
        </svg>
        <span>Tours</span>
      </a>
    </li>
  </ul>

  <div class="legal">
    &copy; 2024 by trillo. Made by unibox following the course Advanced css/sass
    by Jonas Schmedtmann
  </div>
</nav>

<style lang="scss">
  @use '../styles/vars';

  .sidebar {
    background-color: var(--color-grey-dark-1);
    flex: 0 0 18%;
    display: flex;
    justify-content: space-between;
    flex-direction: column;
    min-height: 100svh;
  }

  .side-nav {
    font-size: 1.4rem;
    list-style: none;
    margin-top: 3.5rem;

    @media only screen and (max-width: vars.$bp-medium) {
      display: flex;
      margin: 0;
    }

    &__item {
      position: relative;

      &:not(:last-child) {
        margin-bottom: 0.5rem;

        @media only screen and (max-width: vars.$bp-medium) {
          margin: 0;
        }
      }

      @media only screen and (max-width: vars.$bp-medium) {
        flex: 1;
      }
    }

    &__item::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
      width: 3px;
      background-color: var(--color-primary);
      transition:
        transform 0.2s,
        width 0.4s cubic-bezier(1, 0, 0, 1) 0.2s,
        background-color 0.1s;
      transform: scaleY(0);
      // transform-origin: bottom;
    }

    &__item:hover::before,
    &__item--active::before {
      transform: scaleY(1);
      width: 100%;
    }

    &__item:active::before {
      background-color: var(--color-primary-light);
    }

    &__link:link,
    &__link:visited {
      color: var(--color-grey-light-1);
      text-decoration: none;
      text-transform: uppercase;
      display: block;
      padding: 1.5rem 3rem;
      display: flex;
      align-items: center;
      position: relative; //^ fa far funzionare z-index
      z-index: 10;

      @media only screen and (max-width: vars.$bp-medium) {
        justify-content: center;
        padding: 2rem;
      }

      @media only screen and (max-width: vars.$bp-small) {
        flex-direction: column;
        padding: 1.5rem 0.5rem;
      }
    }

    &__icon {
      height: 1.75rem;
      width: 1.75rem;
      margin-right: 2rem;
      fill: currentColor;

      @media only screen and (max-width: vars.$bp-small) {
        margin-right: 0;
        margin-bottom: 0.7rem;
        height: 1.5rem;
        width: 1.5rem;
      }
    }
  }

  .legal {
    text-align: center;
    color: var(--color-grey-light-4);
    font-size: 1.2rem;
    padding: 2.5rem;

    @media only screen and (max-width: vars.$bp-medium) {
      display: none;
    }
  }
</style>
