<template>
  <v-row
    align="center"
    justify="space-around"
  >
    <v-btn
     class="button"
    >
      <v-icon v-if="showIcon" left>
        {{icon}}
      </v-icon>
      {{label}}
    </v-btn>
  </v-row>
</template>

<script>
  export default {
    name: 'CustomButton',
    props: {
      label: {
        type: String,
        default: ''
      },
      icon: {
        type: String,
        default: ''
      },
      showIcon: {
        type: Boolean,
        default: false
      }
    },

    data: () => ({
    }),
  }
</script>

<style src="./style.scss" lang="scss" scoped></style>