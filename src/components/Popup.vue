<template>
  <div v-if="finalMessage" class="popup-container" id="popup-container">
    <div class="popup">
      <h2>{{ finalMessage }}</h2>
      <h3 v-show="status === 'lose'">...le mot était: {{ word }}</h3>
      <button @click="reset">Jouer encore</button>
    </div>
  </div>
</template>

<script>
import { computed } from "vue";
export default {
  props: {
    status: {
      type: String,
      default: ''
    },
    word: {
      type: String,
      default: ''
    }
  },
  setup(props, { emit }) {
    const finalMessage = computed(() => {
      // Affiche msg en fonction de l'état du jeu
      if (props.status === 'win') return 'Félicitations! vous avez gagné! 🙂'
      if (props.status === 'lose') return 'Malheureusement vous avez perdu! 😕'
      return ''
    })
    const reset = () => emit('reset')
    return { finalMessage, reset }
  }
}
</script>
