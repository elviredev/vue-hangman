<template>
  <div class="notification-container" :class="show ? 'show' : ''">
    <p>Vous avez déja entré cette lettre</p>
  </div>
</template>

<script>
export default {
  props: {
    show: {
      type: Boolean,
      default: false
    }
  }
}
</script>
