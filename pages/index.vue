<template>
  <div>
    <h1>Hello world!</h1>
    <pre>{{ apiResponse }}</pre>
  </div>
</template>

<script>
import axios from 'axios'
axios.defaults.baseURL = 'http://localhost:8000/api/v1'

export default {
  async asyncData() {
    const dataFromLocalHost = await axios.get('message')
    return {
      apiResponse: dataFromLocalHost.data
    }
  }
}
</script>