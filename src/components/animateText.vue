<script setup>
import { onMounted } from "vue";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { TextPlugin } from "gsap/TextPlugin";
import { animateText, animateTextRemove } from "saminate";

gsap.registerPlugin(ScrollTrigger);
gsap.registerPlugin(TextPlugin);
onMounted(() => {
  animateText(
    ".animateTxt",
    "updated text",
    ".animateTextWrap",
    4,
    0,
    "power1.inOut",
    "top center",
    "bottom center",
    "play reset play reset"
  );
  animateTextRemove(
    ".animateTextRem",
    ".animateTextWrap",
    4,
    0,
    "power1.inOut",
    "top center",
    "bottom center",
    "play reset play reset"
  );
});
</script>

<template>
  <div class="animateTextWrap">
    <div class="animateText">
      <h1 class="animateTxt">animateText</h1>
      <p class="descSuggestion">animate a text to update</p>
    </div>
    <div class="animateTextRemove">
      <h1 class="animateTextRem">animateTextRemove</h1>
      <p class="descSuggestion">animate a text to remove</p>
    </div>
  </div>
</template>

<style scoped>
.animateTextWrap {
  display: grid;
  grid-template-columns: 1fr 1fr;
  justify-content: space-evenly;
  align-items: center;
  height: 100vh;
  overflow: hidden;
  width: 100vw;
}
.animateText,
.animateTextRemove {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.animateTxt,
.animateTextRem {
  font-size: clamp(1rem, 5vw, 3rem);
  color: #161616;
  user-select: none;
  margin: 0;
  text-align: center;
  height: clamp(1.5rem, 6vw, 4rem);
}
.descSuggestion {
  font-size: clamp(0.8rem, 3vw, 1.5rem);
  color: #161616;
  user-select: none;
  margin: 0;
  text-align: center;
}
@media (max-width: 1024px) {
  .animateTextWrap {
    display: flex;
    flex-direction: column;
  }
}
</style>
