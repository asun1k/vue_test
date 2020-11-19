<template>
  <div class="home">
    <img  width="350"  alt="Swed logo" src="https://i2.wp.com/insurance-edge.net/wp-content/uploads/2019/10/swedbank-partner-with-munich-re.jpg?fit=693%2C385&ssl=1&w=640">
    <HelloWorld msg="Welcome to SwedBank"/>

  </div>

</template>

<script>

import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>
