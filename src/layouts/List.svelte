<script>
  const listItems = [
    'Close to the beach',
    'Breakfast included',
    'Free airport shuttle',
    'Free wifi in all rooms',
    'Air conditioning and heating',
    'Pets allowed',
    'We speak all languages',
    'Perfect for families',
  ];
</script>

<ul class="list">
  {#each listItems as item (item)}
    <li class="list__item">{item}</li>
  {/each}
</ul>

<style lang="scss">
  @use '../styles/vars';

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
</style>
