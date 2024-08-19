<script>
  import { icons } from '../js/constants.js';
</script>

<form action="" class="search">
  <input type="text" class="search__input" placeholder="Search hotels" />
  <button class="search__button">
    <svg class="search__icon">
      <use xlink:href={`${icons}#icon-magnifying-glass`}></use>
    </svg>
  </button>
</form>

<style lang="scss">
  @use '../styles/vars';

  .search {
    flex: 0 0 40%;

    display: flex;
    justify-content: center;
    align-items: center;

    @media only screen and (max-width: vars.$bp-xsmall) {
      order: 1;
      flex: 0 0 100%;
      background-color: var(--color-grey-light-2);
    }

    &__input {
      font-family: inherit;
      font-size: inherit;
      color: inherit;
      background-color: var(--color-grey-light-2);
      border: none;
      padding: 0.7rem 2rem;
      border-radius: 100px;
      width: 90%;
      transition: all 0.2s;
      margin-right: -3.25rem;

      &::placeholder {
        color: var(--color-grey-light-4);
        font-weight: 100;
      }

      &:focus {
        outline: none;
        width: 100%;
        background-color: var(--color-grey-light-3);
      }
    }

    &__input:focus + &__button {
      background-color: var(--color-grey-light-3);
    }

    &__button {
      border: none;
      background-color: var(--color-grey-light-2);

      &:focus {
        outline: none;
      }

      &:active {
        transform: translateY(2px);
      }
    }

    &__icon {
      height: 2rem;
      width: 2rem;
      fill: var(--color-grey-dark-3);
    }
  }
</style>
