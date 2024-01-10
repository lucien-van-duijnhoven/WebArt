<script setup>

let props = defineProps({
  hash: {
    type: String,
    required: true
  }
})

function setScrollerHook(el) {
  window.addEventListener("scroll", () => {
    let domRect = el.getBoundingClientRect();
    if (domRect.top <= 0 && domRect.top + domRect.height >= 0) {
      let localHash = `#${props.hash}`;
      if (window.location.hash !== localHash) {
        history.replaceState(undefined, undefined, localHash);
      }
    }
  })
}
</script>

<template>
  <section class='artsection' :id='props.hash' :ref='el => { setScrollerHook(el) }'>
    <slot></slot>
  </section>
</template>

<style scoped>
.artsection {
  height: 100vh;
  widows: 100%;
}
</style>
