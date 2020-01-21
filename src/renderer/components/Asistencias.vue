<template>
  <div>
    <modal v-if="loginVisible" @close='close()'></modal>
  </div>
</template>

<script>
import axios from 'axios'
import Modal from './Modal'
export default {
  name: 'asistencias',
  components: { Modal },
  data () {
    return {
      loginVisible: true
    }
  },
  methods: {
    close () {
      this.loginVisible = false
    }
  },
  mounted () {
    axios
      .get('http://dummy.restapiexample.com/api/v1/employees')
      .then(response => {
        console.log(response)
      })
  }
}
</script>

<style></style>
