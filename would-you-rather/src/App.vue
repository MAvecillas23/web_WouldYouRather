<!-- Vue/ JS code goes in script-->
<script setup>
import WouldYouRather from './components/WouldYouRather.vue'

// import this too
import { ref } from 'vue'

// Would you rather question and answers
const wyrQuestion = ref('Live in a house shaped like' +
    ' a triangle or a house shaped like a circle?')
const wyrAnswer1 = ref('Triangle house')
const wyrAnswer2 = ref('Circle house')

// store the user's answer once they made a choice
const userSelection = ref('')

// updates whatever userSelection was changed to
function updateUserSelection(userChoice) {
  userSelection.value = userChoice
}

</script>

<!-- html and Vue models goes inside template-->
<template>
  <div id="app-component">
    <h1>Would You Rather?</h1>
  <!--  assign question and answers that is handled through WouldYouRather.vue's defineProps to the vyrQuestion and answers
   shown above-->
    <WouldYouRather v-bind:question="wyrQuestion"
                    v-bind:answer1="wyrAnswer1"
                    v-bind:answer2="wyrAnswer2"
                    v-on:answer-selected="updateUserSelection">
    </WouldYouRather>
    <p> You chose {{ userSelection }}!</p>
  </div>
 </template>
<!-- CSS goes in style-->
<style scoped>
p {
  font-family: "Courier New", sans-serif;
}

#app-component {
  background-color: greenyellow;
  padding: 40px
}

</style>
