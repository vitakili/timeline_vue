<template>
  <q-layout view="hHh Lpr lff">

    <q-header elevated class="bg-color text-white" height-hint="98">
      <q-toolbar>

        <q-toolbar-title>
          <q-avatar>
            <img src="./assets/vue.svg">
          </q-avatar>
          Timeline for Easy Software
        </q-toolbar-title>

      </q-toolbar>
    </q-header>


    <q-page-container class="container">
      <timeline-list/>
    </q-page-container>

    <q-footer class="bg-grey-8 text-white">
      <q-toolbar>
        <q-toolbar-title>
          <div>Vít Kilián</div>
        </q-toolbar-title>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import TimelineList from './components/TimelineList.vue'

export default {
    components: { TimelineList }
}
</script>

<style lang="scss">

  .bg-color {
    background-color: $cyan-5;
  }

  $xs-breakpoint: 718px;
  $sm-breakpoint: 1024px;
  $md-breakpoint: 1439px;
  $lg-breakpoint: 1920px;

.container,
.container-sm,
.container-md,
.container-lg,
.container-xl {
  width: 100%;
  margin-right: auto;
  margin-left: auto;
}

@media (min-width: $xs-breakpoint) {
  .container,
  .container-sm {
    max-width: 540px;
  }
}

@media (min-width: $sm-breakpoint) {
  .container,
  .container-sm,
  .container-md {
    max-width: 920px;
  }
}

@media (min-width: $md-breakpoint) {
  .container,
  .container-sm,
  .container-md,
  .container-lg {
    max-width: 1140px;
  }
}

@media (min-width: $lg-breakpoint) {
  .container,
  .container-sm,
  .container-md,
  .container-lg,
  .container-xl {
    max-width: 1440px;
  }
}
</style>