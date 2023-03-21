<template>
  <div class="flex flex-col items-center">
    <span class="text-cyan-900 font-bold text-xl">{{counterStore.mainCount}}</span>
    <br>
    <button @click="counterStore.countIncrement()" class="rounded-xl border-2 p-0.5 w-1/4">add</button>
  </div>
</template>
<script>
import { mapState, mapActions, mapStores } from 'pinia'
import {useCounterStore} from "~/stores/counter";
export default {
  computed: {
    // note we are not passing an array, just one store after the other
    // each store will be accessible as its id + 'Store'
    ...mapStores(useCounterStore)
  },
  methods: {
    test() {
      console.log(this.counterStore)
      console.log(this.counterStore.mainCount);
    }
  }
}
</script>
