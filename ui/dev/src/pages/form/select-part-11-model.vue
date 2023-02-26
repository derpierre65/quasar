<template>
  <div class="q-layout-padding column q-gutter-y-lg">
    <q-select
      ref="input"
      v-model="model"
      :options="options"
      label="Value"
      color="white"
      square
      dense
      outlined
      use-input
      fill-input
      hide-selected
      @filter="search">
      <template #option="{opt}">
        <q-item v-close-popup clickable @click="select(opt.value)">
          <q-item-section>
            <q-item-label v-html="opt.label" />
          </q-item-section>
        </q-item>
      </template>
    </q-select>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    return {
      model: ref(''),
      options: ref([])
    }
  },
  methods: {
    select (value) {
      this.model = value
    },
    search (value, update, abort) {
      update(() => {
        this.options = [
          { label: 'Hello', value: 'HEllO' }
        ]
      })
    }
  }
}
</script>
