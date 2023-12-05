# hello vitepress
<component v-if="dynamicComponent" :is="dynamicComponent"></component>

<script setup>
import {onMounted,ref} from "vue"

const dynamicComponent = ref();
onMounted(() => {
  import('./test.vue').then((module) => {
    dynamicComponent.value = module.default
  })
})
</script>