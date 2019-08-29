<template>
  <div class="main-page">
    <carousel />
    <lists />
  </div>
</template>

<script>
import carousel from './carousel'
import lists from './lists'

export default {
  name: 'index',
  components: {
    carousel,
    lists
  },
  data: () => ({
    
  })
}
</script>

