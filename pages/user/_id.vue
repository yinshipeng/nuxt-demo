<template>
    <div>
        this is template body-- ID: {{id}}
    </div>
</template>
<script>
    export default{
      data () {
        return {
          msg: 'hello vue',
          id: ''
        }
      },
      validate ({ params }) {
        // Must be a number
        return /^\d+$/.test(params.id)
      },
      created () {
        this.id = this.$route.params.id
      }
    }
</script>
<style>
</style>
