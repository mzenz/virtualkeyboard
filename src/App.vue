<style>
.container {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}

.button {
  background-color: lime;
}

.hidden {
  opacity: 0;
  display: fixed;
  z-index: -100;
}
</style>

<template>
  <div class="container">
    <button class="button" @click="onButtonPress">show virtual keyboard</button>
    <input
      ref="input"
      class="hidden"
      @input="onInput"
      @keypress="onKeyPress"
      @keydown="onKeyDown"
      @keyup="onKeyUp"
      @focus="onInputFocus"
      @blur="onInputBlur"
    />
  </div>
</template>

<script setup lang="ts">
const input = $ref<HTMLInputElement>()

const onButtonPress = () => {
  console.debug('onButtonPress()')
  input?.focus()
}

const onInputFocus = () => {
  console.debug('onInputFocus()')
}

const onInputBlur = () => {
  console.debug('onInputBlur()')
}

const onInput = (e: InputEvent) => {
  console.debug('onInput:')
  console.debug(e.data)
}

const onKeyDown = (e: KeyboardEvent) => {
  console.debug('onKeyDown:')
  console.debug(e)
  console.debug(e.keyCode)
}

const onKeyPress = (e: KeyboardEvent) => {
  console.debug('onKeyPress:')
  console.debug(e)
  console.debug(e.keyCode)
}

const onKeyUp = (e: KeyboardEvent) => {
  console.debug('onKeyUp:')
  console.debug(e)
  console.debug(e.keyCode)
}
</script>
