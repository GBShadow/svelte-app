<script lang="ts">
  import MeetupItem from './MeetupItem.svelte'
  import type { Meetup } from '../types/Meetup'

  export let meetups: Meetup[]
</script>

<section>
  {#each meetups as meetup (meetup.id)}
    <MeetupItem {meetup} />
  {/each}
</section>

<style>
  section {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr;
    grid-gap: 1rem;
  }

  @media (min-width: 768px) {
    section {
      grid-template-columns: repeat(2, 1fr);
    }
  }
</style>
