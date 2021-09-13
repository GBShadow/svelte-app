<script lang="ts">
  import type { Meetup } from './types/Meetup'
  import MeetupGrid from './Meetups/MeetupGrid.svelte'

  import Header from './UI/Header.svelte'
  import TextInput from './UI/TextInput.svelte'

  let meetups: Meetup[] = [
    {
      id: 'm1',
      title: 'Coding Bootcamp',
      subtitle: 'Learn to code in 2 hours',
      description:
        'In this meetups, we will have some experts that teach you how to code',
      imageURL:
        'https://images.pexels.com/photos/169573/pexels-photo-169573.jpeg?auto=compress&cs=tinysrgb&dpr=3&h=750&w=1260',
      address: '27th Nerd Road, 32523 New York',
      contactEmail: 'code@test.com',
    },
    {
      id: 'm2',
      title: 'Swim Together',
      subtitle: "Let's go swimming",
      description: 'We will simply swim some rounds',
      imageURL:
        'https://images.pexels.com/photos/863988/pexels-photo-863988.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=650&w=940',
      address: '27th Nerd Road, 32523 New York',
      contactEmail: 'swim@test.com',
    },
  ]

  let id = Math.random().toString()
  let title = ''
  let subtitle = ''
  let description = ''
  let imageURL = ''
  let address = ''
  let contactEmail = ''

  const handleSubmit = () => {
    meetups = [
      {
        id,
        title,
        subtitle,
        description,
        imageURL,
        address,
        contactEmail,
      },
      ...meetups,
    ]
  }
</script>

<Header />

<main>
  <form on:submit|preventDefault={handleSubmit}>
    <TextInput label="Title" id="title" bind:value={title} />
    <TextInput label="Subtitle" id="subtitle" bind:value={subtitle} />
    <TextInput
      label="Description"
      id="description"
      textarea
      bind:value={description}
    />
    <TextInput label="Address" id="address" bind:value={address} />
    <TextInput label="Image URL" id="imageURL" bind:value={imageURL} />
    <TextInput
      label="Contact Email"
      id="contactEmail"
      bind:value={contactEmail}
    />
    <button type="submit">Save</button>
  </form>

  <MeetupGrid {meetups} />
</main>

<style>
  main {
    margin-top: 5rem;
    padding-bottom: 1rem;
  }
</style>
