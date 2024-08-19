<script>
  import { base } from '../js/constants';
  import ButtonInline from '../lib/Button-inline.svelte';
  import List from './List.svelte';
  import Paragraph from '../lib/Paragraph.svelte';
  import Reccomend from './Reccomend.svelte';
  import Review from '../lib/Review.svelte';

  const mask = base + '/img/chevron-thin-right.svg';
</script>

<div class="details">
  <div class="description">
    <Paragraph />
    <Paragraph />
    <List />
    <Reccomend />
  </div>

  <div class="user-reviews">
    <Review name="Nick Smith" date="Feb 23rd, 2024" rating="7.8" user="1" />
    <Review name="Mary Thomas" date="Sept 13th, 2024" rating="9.3" user="2" />

    <ButtonInline>Show all <span>&rarr;</span></ButtonInline>
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

  .user-reviews {
    flex: 1;
    // background-color: #9d4;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
</style>
