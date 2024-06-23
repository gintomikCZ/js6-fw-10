
<template>
  <div>{{ label }}</div>
  <div>{{ counter }}</div>
  <button @click="increment">plus</button>
  <div>{{ greeting }}</div>
  <button @click="setFirstname('Franta')">set to Franta</button>
  <button @click="setFullName('Jenda Benda')">set to jenda</button>
</template>

<script setup>
  import { ref, computed, onMounted, onBeforeMount } from 'vue'

  defineProps({
    label: {
      type: String,
      default: 'i am label'
    }
  })

  // code about counter functionality
  const counter = ref(1)
  const increment = () => {
    counter.value += 1
  }
  // -----------



  // code about something else
  const firstname = ref('Karel')
  const lastname = ref('Houska')


  const fullname = computed({
      get () {
        return firstname.value + ' ' + lastname.value
      },
      set (str) {
        const splited = str.split(' ')
        firstname.value = splited[0]
        lastname.value = splited[1]
      }
    })

  function setFullName (str) {
    fullname.value = str
  }


  const greeting = computed(() => {
    return 'hello ' + fullname.value
  })
  const setFirstname = (name) => {
    firstname.value = name
  }

  onBeforeMount(() => {
    console.log('beforeMount')
  })

  onMounted(() => {
    console.log('mounted')
  })



</script>
