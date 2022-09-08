<template>
<div id="q-app" style="min-height: 100vh;">
  <div class="q-px-lg q-pb-md">

      <q-timeline :layout="layout" color="cyan-5">
        <q-timeline-entry heading>
          Timeline heading
          <br />
        </q-timeline-entry>

      <timeline-item
      v-for="(item, i) in sortedItems"
      :key="item._id"
      :title="item.name.first + ' ' + item.name.last"
      :subtitle="item.registered"
      :about="item.about"
      :tags="item.tags"
      :side="i % 2 ? 'right' : 'left'"
      />

        </q-timeline>
    </div>
  </div>
</template>

<script>
import { useQuasar } from 'quasar'
import timeline from "../json/timeline.json";
import TimelineItem from './TimelineItem.vue';

export default {
  name: 'TimelineList',
  components: { TimelineItem },
    data() {
        return {
            data: timeline,
        };
    },
    computed: {
        layout: () => {
            const $q = useQuasar();
            return $q.screen.lt.sm ? "dense" : ($q.screen.lt.md ? "comfortable" : "loose");
        },
        sortedItems: function () {
            const sorted = this.data;
            return sorted.sort((a, b) => new Date(a.registered) - new Date(b.registered));
        },
    },
};
</script>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
