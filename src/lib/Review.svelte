<script>
  import { base } from '../js/constants';
  const { name, date, rating, user } = $props();
</script>

<figure class="review">
  <blockquote class="review__text">
    Lorem ipsum dolor sit, amet consectetur adipisicing elit. Maxime earum
    quibusdam nesciunt laborum? At, similique!
  </blockquote>
  <figcaption class="review__user">
    <img
      class="review__photo"
      src={`${base}/img/user-${user}.jpg`}
      alt="User 1" />

    <div class="review__user-box">
      <p class="review__user-name">{name}</p>
      <p class="review__user-date">{date}</p>
    </div>
    <div class="review__rating">{rating}</div>
  </figcaption>
</figure>

<style lang="scss">
  @use '../styles/vars';

  .review {
    background-color: #fff;
    box-shadow: var(--shadow-light);
    padding: 3rem;
    margin-bottom: 3.5rem;
    position: relative;
    overflow: hidden;

    @media only screen and (max-width: vars.$bp-medium) {
      padding: 2rem;
      margin-bottom: 3rem;
    }

    @media only screen and (max-width: vars.$bp-small) {
    }

    &__text {
      margin-bottom: 2rem;
      z-index: 1;
      position: relative;
    }

    &__user {
      display: flex;
      align-items: center;
    }

    &__photo {
      height: 4.5rem;
      width: 4.5rem;
      border-radius: 50%;
      margin-right: 1.5rem;
    }

    &__user-box {
      margin-right: auto;
    }

    &__user-name {
      font-size: 1.1rem;
      font-weight: 600;
      text-transform: uppercase;
      margin-bottom: 0.4rem;
    }

    &__user-date {
      font-size: 1rem;
      color: var(--color-grey-dark-3);
    }

    &__rating {
      color: var(--color-primary);
      font-size: 2.2rem;
      font-weight: 300;
    }

    &::before {
      content: '\201C';
      position: absolute;
      top: -3rem;
      left: -1rem;
      font-size: 20rem;
      font-family: sans-serif;
      line-height: 1;
      color: var(--color-grey-light-2);
      z-index: 1;
    }
  }
</style>
