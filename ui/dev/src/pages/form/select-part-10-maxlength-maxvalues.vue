<template>
  <div class="q-layout-padding column q-gutter-y-lg">
    <q-select
      v-model="tags"
      :max-values="10"
      label="Tags"
      new-value-mode="add-unique"
      input-debounce="0"
      color="white"
      maxlength="25"
      counter
      use-input
      use-chips
      multiple
      square
      outlined
      dense
      hide-dropdown-icon
      @new-value="addTag" />
  </div>
</template>

<script>
import {ref} from "vue";

export default {
  setup() {
    return {
      tags: ref([]),
    }
  },
  methods: {
    addTag(val, done) {
      done(val);
    },
  }
}
</script>
