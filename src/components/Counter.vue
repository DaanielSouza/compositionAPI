
<template lang="pt-Br">
  <div>
    <p>Valor inicial: {{ initialValue }}</p>
    <p>Atual {{ count }}</p>
    <p>Triplo {{tripple}}</p>
    <button @click="add">Add</button><br>
  </div>
</template>
<script>
import { ref, computed, watch, onMounted } from 'vue';

export default {
  name: "CounterComponent",
  props: {
    initialValue: Number
  },
  setup(props) {
    const count = ref(props.initialValue)

    const add = () => {
      count.value++;
    }

    const tripple = computed(() => count.value * 3);

    watch(count, (newV, oldV) => {
      console.log(oldV, newV);
    });

    onMounted(()=>{
      console.log("Montado")
    });

    return { count, add, tripple }
  }
}
</script>
<style lang="pt-Br" scoped>
  
</style>