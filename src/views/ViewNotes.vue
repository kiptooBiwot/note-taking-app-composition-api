<template>
  <div class="notes">
    <div class="card has-background-danger-dark mb-5 p-4">
      <div class="field">
        <div class="control">
          <textarea
            class="textarea"
            placeholder="Add a new note"
          />
        </div>
      </div>

      <div class="field is-grouped is-grouped-right">
        <div class="control">
          <button class="button is-link has-background-danger">Add New Note</button>
        </div>
      </div>
    </div>
    <div v-for="i in 3"  class="card mb-4">
      <header class="card-header">
      </header>
      <div class="card-content">
        <div class="content">
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Atque eum, nam ab velit culpa quibusdam excepturi expedita itaque accusamus eius corporis dignissimos. Dolore, libero? Sequi quod labore cupiditate quisquam natus.
        </div>
      </div>
      <footer class="card-footer">
        <!-- <a href="#" class="card-footer-item">Save</a> -->
        <a href="#" class="card-footer-item">Edit</a>
        <a href="#" class="card-footer-item">Delete</a>
      </footer>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>

</style>