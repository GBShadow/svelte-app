<script lang="ts">
  export let label: string
  export let id: string
  export let textarea: boolean | undefined = undefined
  export let value: string
</script>

<div class="form-control">
  <label for={id}>{label}</label>
  {#if textarea}
    <textarea rows="3" {id} bind:value />
  {:else}
    <input type="text" {id} bind:value />
  {/if}
</div>

<style>
  textarea,
  input {
    border-color: #e40763;
    outline: 0;
  }

  label {
    display: block;
    margin-bottom: 0.5rem;
    width: 100%;
  }

  .form-control {
    padding: 0.5rem 0;
    width: 100%;
    margin: 0.25rem 0;
  }
</style>
