<template>
  <div class="main-page">
    <carousel />
    <lists />
    <collapse />
  </div>
</template>

<script>
import carousel from './carousel'
import lists from './lists'
import collapse from './collapse'

export default {
  name: 'index',
  components: {
    carousel,
    lists,
    collapse
  }
}
</script>

