<script>
  import { icons } from '../js/constants';
  let { icon, label, activeLink = $bindable() } = $props();
</script>

<li
  class={`side-nav__item side-nav__item--${activeLink === label ? 'active' : ''}`}>
  <a href="#" class="side-nav__link" onclick={() => (activeLink = label)}>
    <svg class="side-nav__icon">
      <use xlink:href={`${icons}#icon-${icon}`}></use>
    </svg>
    <span>{label}</span>
  </a>
</li>

<style lang="scss">
  @use '../styles/vars';

  .side-nav {
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
</style>
