<script setup>
import figlet from 'figlet';
import standard from 'figlet/importable-fonts/Standard.js'
import { ref } from 'vue'

figlet.parseFont("Standard", standard);

const msg = ref('Terve asciita!muutos1')

const update = (msg) => {
    return figlet.textSync(
    msg,
    {
      font: "Standard",
      whitespaceBreak: "True",
    },
  );
}

</script>

<template>
  <div>
    <input v-model="msg" />
    <pre class="gradient">{{ update(msg) }}</pre>
  </div>

</template>

<style scoped>


@keyframes animatedTextGradient {
  to {
    background-position: 200% top;
  }
}

.gradient {
  background: radial-gradient(
    circle at 50%,
    #b2a80d,
    #0d00fb 30%,
    #c7d20e 55%,
    #9a8d0d 95%
  );
  font-weight: 600;
  background-size: 200% auto;
  color: #000;
  background-clip: text;
  -webkit-text-fill-color: transparent;
  animation: animatedTextGradient 4s linear infinite;
}
</style>
