<script>
  import { base, icons } from '../js/constants';
  const mask = base + '/img/chevron-thin-right.svg';
</script>

<div class="details">
  <div class="description">
    <p class="paragraph">
      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Et aspernatur
      deleniti soluta id pariatur inventore excepturi, officiis fuga incidunt
      iure iste nobis qui quos itaque!
    </p>
    <p class="paragraph">
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aut ullam
      veritatis, deserunt sapiente obcaecati accusamus!
    </p>

    <ul class="list">
      <li class="list__item">Close to the beach</li>
      <li class="list__item">Breakfast included</li>
      <li class="list__item">Free airport shuttle</li>
      <li class="list__item">Free wifi in all rooms</li>
      <li class="list__item">Air conditioning and heating</li>
      <li class="list__item">Pets allowed</li>
      <li class="list__item">We speak all languages</li>
      <li class="list__item">Perfect for families</li>
    </ul>
    <div class="recommend">
      <p class="recommend__count">
        Lucy and 3 other friends recommend this hotel.
      </p>

      <div class="recommend__friends">
        <img
          src={`${base}/img/user-3.jpg`}
          alt="Friend 1"
          class="recommend__photo" />
        <img
          src={`${base}/img/user-4.jpg`}
          alt="Friend 2"
          class="recommend__photo" />
        <img
          src={`${base}/img/user-5.jpg`}
          alt="Friend 3"
          class="recommend__photo" />
        <img
          src={`${base}/img/user-6.jpg`}
          alt="Friend 4"
          class="recommend__photo" />
      </div>
    </div>
  </div>

  <div class="user-reviews">
    <figure class="review">
      <blockquote class="review__text">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Maxime earum
        quibusdam nesciunt laborum? At, similique!
      </blockquote>
      <figcaption class="review__user">
        <img
          class="review__photo"
          src={`${base}/img/user-1.jpg`}
          alt="User 1" />

        <div class="review__user-box">
          <p class="review__user-name">Nick Smith</p>
          <p class="review__user-date">Feb 23rd, 2024</p>
        </div>
        <div class="review__rating">7.8</div>
      </figcaption>
    </figure>

    <figure class="review">
      <blockquote class="review__text">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Maxime earum
        quibusdam nesciunt laborum? At, similique!
      </blockquote>
      <figcaption class="review__user">
        <img
          class="review__photo"
          src={`${base}/img/user-2.jpg`}
          alt="User 2" />
        <div class="review__user-box">
          <p class="review__user-name">Mary Thomas</p>
          <p class="review__user-date">Sept 13th, 2024</p>
        </div>
        <div class="review__rating">9.3</div>
      </figcaption>
    </figure>

    <button class="btn-inline">Show all <span>&rarr;</span></button>
  </div>
</div>

<style lang="scss">
  @use '../styles/vars';

  .details {
    font-size: 1.4rem;
    display: flex;
    padding: 4.5rem;
    background-color: var(--color-grey-light-1);
    border-bottom: var(--line);

    @media only screen and (max-width: vars.$bp-medium) {
      padding: 3rem;
    }

    @media only screen and (max-width: vars.$bp-small) {
      flex-direction: column;
      padding: 0;
    }
  }

  .description {
    background-color: #fff;
    box-shadow: var(--shadow-light);
    padding: 3rem;
    flex: 0 0 60%;
    margin-right: 4.5rem;

    @media only screen and (max-width: vars.$bp-medium) {
      padding: 2rem;
      margin-right: 3rem;
    }

    @media only screen and (max-width: vars.$bp-small) {
      margin-right: 0;
      margin-bottom: 3rem;
    }
  }

  .btn-inline {
    border: none;
    color: var(--color-primary);
    font-size: inherit;
    border-bottom: 1px solid currentColor;
    padding-bottom: 2px;
    display: inline-block;
    background-color: transparent;
    cursor: pointer;
    transition: all 0.2s;

    span {
      margin-left: 3px;
      transition: margin-left 0.2s;
    }

    &:hover {
      color: var(--color-grey-dark-1);

      span {
        margin-left: 8px;
      }
    }

    &:focus {
      outline: none;
      animation: pulsate 1s infinite;
    }
  }

  @keyframes pulsate {
    0% {
      transform: scale(1);
      box-shadow: none;
    }
    50% {
      transform: scale(1.05);
      box-shadow: 0 1rem 4rem rgba(0, 0, 0, 0.25);
    }
    100% {
      transform: scale(1);
      box-shadow: none;
    }
  }

  .paragraph:not(:last-of-type) {
    margin-bottom: 2rem;
  }

  .list {
    list-style: none;
    margin: 3rem 0;
    padding: 3rem 0;
    border-top: var(--line);
    border-bottom: var(--line);

    display: flex;
    flex-wrap: wrap;

    &__item {
      flex: 0 0 50%;
      margin-bottom: 0.7rem;

      flex-direction: column;
    }

    &__item::before {
      content: '';
      display: inline-block;
      height: 1rem;
      width: 1rem;
      margin-right: 0.7rem;

      // older browsers
      // background-image: url("../img/chevron-thin-right.svg");
      // background-size: cover;

      // newer browsers "masks"
      background-color: var(--color-primary);
      mask-image: url('/trillo-scss-svelte/img/chevron-thin-right.svg');
      mask-size: cover;
    }
  }

  .recommend {
    font-size: 1.3rem;
    color: var(--color-grey-dark-3);
    display: flex;
    align-items: center;

    &__count {
      margin-right: auto;
    }

    &__friends {
      display: flex;
    }

    &__photo {
      box-sizing: content-box;
      height: 4rem;
      width: 4rem;
      border-radius: 50%;
      border: 3px solid #fff;
      &:not(:last-child) {
        margin-right: -1.5rem;
      }
    }
  }

  .user-reviews {
    flex: 1;
    // background-color: #9d4;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

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
