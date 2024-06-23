<template>
  <div>i am an Option API component</div>
</template>

<script>

export default {
  data () {
    return {
      first: 'Láďa',
      last: 'Novák'
    }
  },
  computed: {
    full () {
      return this.first + ' ' + this.last
    }
  }
}



</script>


