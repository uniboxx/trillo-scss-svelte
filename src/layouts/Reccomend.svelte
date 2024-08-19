<script>
  import { base } from '../js/constants';
  const friends = 4;
</script>

<div class="recommend">
  <p class="recommend__count">
    {`Lucy and ${friends - 1} other friends recommend this hotel.`}
  </p>

  <div class="recommend__friends">
    {#each new Array(4) as friend, idx (idx)}
      <img
        src={`${base}/img/user-${idx + 3}.jpg`}
        alt={`friend ${idx + 1}`}
        class="recommend__photo" />
    {/each}
  </div>
</div>

<style lang="scss">
  @use '../styles/vars';

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
</style>
