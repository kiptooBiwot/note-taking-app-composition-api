<script setup>
import { computed } from '@vue/reactivity';


  const props = defineProps({
    note: {
      type: Object,
      default: null
    }
  })

  /*
    Define emits
  */
 const emits = defineEmits(['deleteClicked'])

  /*
    Computed methods
  */
  const characterLength = computed(() => {
    const length = props.note.content.length
    const description = length  > 1 ? 'characters' : 'character'
    return length + ' ' + description
  })

  /*
    Methods
  */
  const handleDeleteClicked = () => {
    emits('deleteClicked', props.note.id)
  }
</script>

<template>
  <div
      class="card mb-4"
    >
      <header class="card-header">
      </header>
      <div class="card-content">
        <div class="content">
          {{ note.content }}
          <div class="has-text-right has-text-grey-light mt-2">
            <small>{{ characterLength }}</small>
          </div>
        </div>
      </div>
      <footer class="card-footer">
        <!-- <a href="#" class="card-footer-item">Save</a> -->
        <a href="#" class="card-footer-item">Edit</a>
        <a
          @click.prevent="handleDeleteClicked"
          class="card-footer-item"
          href="#"
        >
          Delete

        </a>
      </footer>
    </div>
</template>


<style lang="scss" scoped>

</style>