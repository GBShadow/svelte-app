<script lang="typescript">
  import type { Meetup } from '../types/Meetup'

  export let meetup: Meetup
</script>

<article>
  <header>
    <h1>{meetup.title}</h1>
    <h2>{meetup.subtitle}</h2>
    <p>{meetup.address}</p>
  </header>
  <div class="image">
    <img src={meetup.imageURL} alt={meetup.title} />
  </div>
  <div class="content">
    <p>{meetup.description}</p>
  </div>
  <footer>
    <a href="mailto:{meetup.contactEmail}">Contact</a>
    <button>Show Details</button>
    <button>Favorites</button>
  </footer>
</article>

<style>
  article {
    display: flex;
    flex-direction: column;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    border-radius: 5px;
    background: #fff;
    margin: 2rem 1rem;
  }

  header,
  .content,
  footer {
    padding: 1rem;
  }

  .content {
    height: 100%;
  }

  .image {
    width: 100%;
    height: 14rem;
  }

  .image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  h1 {
    font-size: 1.25rem;
    margin: 0.5rem 0;
    font-family: 'Roboto Slab', sans-serif;
  }

  h1.is-favorite {
    background: #01a129;
    color: white;
    padding: 0 0.5rem;
    border-radius: 5px;
  }

  h2 {
    font-size: 1rem;
    color: #808080;
    margin: 0.5rem 0;
  }

  p {
    font-size: 1.25rem;
    margin: 0;
  }

  div {
    text-align: right;
  }

  a {
    border: 1px solid #cf0056;
    padding: 0.4em;
    transition: all 0.5s;
  }

  a:hover {
    background-color: #cf0056;
    color: white;
  }

  footer {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
</style>
