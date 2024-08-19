<script>
  import { base, icons } from '../js/constants';
</script>

<nav class="user-nav">
  <div class="user-nav__icon-box">
    <svg class="user-nav__icon">
      <use xlink:href={`${icons}#icon-bookmark`}></use>
    </svg>
    <span class="user-nav__notification">7</span>
  </div>
  <div class="user-nav__icon-box">
    <svg class="user-nav__icon">
      <use xlink:href={`${icons}#icon-chat`}></use>
    </svg>
    <span class="user-nav__notification">13</span>
  </div>
  <div class="user-nav__user">
    <img
      src={`${base}/img/user.jpg`}
      alt="User photo"
      class="user-nav__user-photo" />
    <span class="user-nav__user-name">Jonas</span>
  </div>
</nav>

<style lang="scss">
  @use '../styles/vars';

  .user-nav {
    align-self: stretch;

    display: flex;
    align-items: center;

    & > * {
      padding: 0 2rem;
      cursor: pointer;
      height: 100%;
      display: flex;
      justify-content: center;
      align-items: center;

      &:hover {
        background-color: var(--color-grey-light-2);
      }
    }

    &__icon-box {
      position: relative;
    }

    &__icon {
      height: 2.25rem;
      width: 2.25rem;
      fill: var(--color-grey-dark-2);
    }

    &__notification {
      font-size: 0.8rem;
      height: 1.75rem;
      width: 1.75rem;
      border-radius: 50%;
      background-color: var(--color-primary);
      color: #fff;
      position: absolute;
      top: 1.5rem;
      right: 1.1rem;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    &__user-photo {
      height: 3.75rem;
      border-radius: 50%;
      margin-right: 1rem;
    }
  }
</style>
