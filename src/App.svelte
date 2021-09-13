<script lang="ts">
  import MeetupGrid from './Meetups/MeetupGrid.svelte'

  import Header from './UI/Header.svelte'

  const meetups = [
    {
      id: 'm1',
      title: 'Coding Bootcamp',
      subtitle: 'Learn to code in 2 hours',
      description:
        'In this meetups, we will have some experts that teach you how to code',
      imageUrl:
        'https://images.pexels.com/photos/169573/pexels-photo-169573.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260',
      address: '27th Nerd Road, 32523 New York',
      contactEmail: 'code@test.com',
    },
    {
      id: 'm2',
      title: 'Swim Together',
      subtitle: "Let's go swimming",
      description: 'We will simply swim some rounds',
      imageUrl:
        'https://images.pexels.com/photos/863988/pexels-photo-863988.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940',
      address: '27th Nerd Road, 32523 New York',
      contactEmail: 'swim@test.com',
    },
  ]
</script>

<Header />

<main>
  <MeetupGrid {meetups} />
</main>

<style>
  main {
    margin-top: 5rem;
    padding-bottom: 1rem;
  }
</style>
