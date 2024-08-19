<script>
  import { icons } from '../js/constants';
  import SideNavItem from '../lib/Side-nav-item.svelte';

  const sideNavItems = [
    { icon: 'home', label: 'Home' },
    { icon: 'aircraft-take-off', label: 'Flight' },
    { icon: 'key', label: 'Car rental' },
    { icon: 'map', label: 'Tours' },
  ];

  let activeLink = $state('Home');
</script>

<nav class="sidebar">
  <ul class="side-nav">
    {#each sideNavItems as item (item.label)}
      <SideNavItem icon={item.icon} label={item.label} bind:activeLink />
    {/each}
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
  }

  .side-nav {
    font-size: 1.4rem;
    list-style: none;
    margin-top: 3.5rem;

    @media only screen and (max-width: vars.$bp-medium) {
      display: flex;
      margin: 0;
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
