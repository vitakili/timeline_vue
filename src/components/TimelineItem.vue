<template>
          <q-timeline-entry
          :title="this.title"
          :subtitle="this.subtitle"
        >
          <div>
            {{ this.about }}
          </div>
          <div v-if="this.tags.length > 0">
                <div v-for="(tag, i) in this.tags" :key="i" class="text-subtitle2">
                  {{ tag }}
                </div>
          </div>
        </q-timeline-entry>
</template>

<script>
export default {
    name:'TImelineItem',
    props:{
        title: {
      type: String,
      default: '',
    },
    subtitle: {
      type: String,
      default: '',
    },
    about: {
      type: String,
      default: '',
    },
    tags: {
        type: Array,
        default: []
    }
    }
}
</script>

<style>

</style>