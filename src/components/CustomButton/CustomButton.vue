<template>
  <v-btn class="button">{{label}}</v-btn>
</template>

<script>
  export default {
    name: 'CustomButton',
    props: {
      label: {
        type: String,
        default: ''
      }
    },

    data: () => ({
    }),
  }
</script>

<style src="./style.scss" lang="scss" scoped></style>