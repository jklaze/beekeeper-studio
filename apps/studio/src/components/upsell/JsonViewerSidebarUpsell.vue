<template>
  <div class="community-overlay">
    <span class="title">
      <i class="material-icons">stars</i> JSON Row Viewer
    </span>
    <div v-if="$store.getters.hideUpsells" class="body">
      <p>
        The JSON Row Viewer is not available in the Community Edition.
      </p>
    </div>
    <div v-else class="body">
      <p>
        Upgrade required to use the JSON Row Viewer.
      </p>
      <p>
        View any row as JSON. Super useful when working with wide tables or complex nested data.
      </p>
    </div>
    <upsell-buttons />
  </div>
</template>
<script lang="js">
import UpsellButtons from './common/UpsellButtons.vue';

  export default {
    components: { UpsellButtons },
    data: () => ({}),
    methods: {
      startTrial() {
        this.$store.dispatch('licenses/add', { trial: true })
      }
    }
  }

</script>
