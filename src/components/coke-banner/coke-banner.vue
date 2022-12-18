<script setup lang="ts">
import { ref, onMounted, getCurrentInstance } from 'vue';

const app = getCurrentInstance();
const gsap = app!.appContext.config.globalProperties.globalAnimation;

const literallyRef = ref();
const canRef = ref();
const sparkle1Ref = ref();
const sparkle2Ref = ref();
const sparkle3Ref = ref();
const limitedRef = ref();
const nowRef = ref();
const inRef = ref();
const storeRef = ref();
const logoRef = ref();

function sceneLiterally() {
  const tl = gsap.timeline();
  tl
    .from(literallyRef.value,
      {
        x: "-100%",
      },
    )
    .to(literallyRef.value,
      {
        duration: 1,
        x: 0,
        ease: "power4.out",
      },
    )
    .to(literallyRef.value,
      {
        duration: 1,
        x: "-100%",
        ease: "sine.out",
        delay: 3,
      },
    );
  return tl;
};

function sceneCan() {
  const tl = gsap.timeline();
  tl
    .from(canRef.value,
      {
        x: "100%",
      },
    )
    .to(canRef.value,
      {
        duration: 1,
        x: 0,
        ease: "power4.out",
      },
    )
    .to(canRef.value,
      {
        duration: 1,
        x: "100%",
        ease: "sine.out",
        delay: 2.5,
      },
    );
  return tl;
};

function sceneSparkle() {
  const tl = gsap.timeline();
  tl
    .from(
      [
        sparkle1Ref.value,
        sparkle2Ref.value,
        sparkle3Ref.value,
      ],
      {
        opacity: 0,
        rotation: 0,
      },
    )
    .to(
      [
        sparkle1Ref.value,
        sparkle2Ref.value,
        sparkle3Ref.value,
      ],
      {
        opacity: 1,
        duration: 2,
        rotation: 60,
      },
      "-=0.5"
    )
    .to(
      [
        sparkle1Ref.value,
        sparkle2Ref.value,
        sparkle3Ref.value,
      ],
      {
        duration: 12,
        rotation: 180,
      },
      "-=1"
    )
    .to(
      [
        sparkle1Ref.value,
        sparkle2Ref.value,
        sparkle3Ref.value,
      ],
      {
        opacity: 0,
        duration: 2,
      },
      "-=4"
    );
  return tl;
};

function sceneLimited() {
  const tl = gsap.timeline();
  tl
    .from(limitedRef.value,
      {
        y: "-100%",
      },
    )
    .to(limitedRef.value,
      {
        duration: 1,
        y: 0,
        ease: "circ.out",
      },
    )
    .to(limitedRef.value,
      {
        duration: 1,
        y: "100%",
        ease: "sine.out",
        delay: 3.5,
      },
    );
  return tl;
};

function sceneNow() {
  const tl = gsap.timeline();

  tl
    .from(nowRef.value,
      {
        y: "100%",
      },
    )
    .to(nowRef.value,
      {
        duration: 1,
        y: 0,
        ease: "circ.out",
      },
    )
    .to(nowRef.value,
      {
        duration: 1,
        y: "100%",
        ease: "sine.out",
        delay: 3,
      },
    );
  return tl;
};

function sceneIn() {
  const tl = gsap.timeline();

  tl
    .from(inRef.value,
      {
        y: "100%",
      },
    )
    .to(inRef.value,
      {
        duration: 1,
        y: 0,
        ease: "circ.out",
      },
    )
    .to(inRef.value,
      {
        duration: 1,
        y: "100%",
        ease: "sine.out",
        delay: 2.5,
      },
    );
  return tl;
};

function sceneStore() {
  const tl = gsap.timeline();

  tl
    .from(storeRef.value,
      {
        y: "100%",
      },
    )
    .to(storeRef.value,
      {
        duration: 1,
        y: 0,
        ease: "circ.out",
      },
    )
    .to(storeRef.value,
      {
        duration: 1,
        y: "100%",
        ease: "sine.out",
        delay: 2,
      },
    );
  return tl;
};

function sceneLogo() {
  const tl = gsap.timeline();

  tl
    .from(logoRef.value,
      {
        opacity: 0,
      },
    )
    .to(logoRef.value,
      {
        duration: 1,
        opacity: 1,
        ease: "circ.out",
      },
    )
  return tl;
};

onMounted(() => {
  gsap.timeline()
    .add(sceneLiterally()).delay(1)
    .add(sceneCan(), "-=5")
    .add(sceneSparkle(), "-=4.5")
    .add(sceneLimited(), "-=8")
    .add(sceneNow(), "-=7.5")
    .add(sceneIn(), "-=7")
    .add(sceneStore(), "-=6.5")
    .add(sceneLogo(), "-=2");
});
</script>

<template>
  <div class="container">
    <div class="coke-banner">
      <img 
        ref="canRef" 
        class="coke-banner__coke-can" 
        src="@/assets/can.png" 
      />
      <img 
        ref="literallyRef" 
        class="coke-banner__text-literally" 
        src="@/assets/literally.png"
      />
      <img 
        ref="limitedRef" 
        class="coke-banner__text-limited" 
        src="@/assets/limited.png"
      />
      <img 
        ref="nowRef" 
        class="coke-banner__text-now" 
        src="@/assets/now.png"
      />
      <img
        ref="inRef" 
        class="coke-banner__text-in" 
        src="@/assets/in.png"
      />
      <img 
        ref="storeRef" 
        class="coke-banner__text-store" 
        src="@/assets/store.png"
      />
      <img 
        ref="logoRef" 
        class="coke-banner__logo" 
        src="@/assets/logo.png"
      />
      <img 
        ref="sparkle1Ref" 
        class="coke-banner__sparkle-1" 
        src="@/assets/sparkle_1.png"
      />
      <img 
        ref="sparkle2Ref" 
        class="coke-banner__sparkle-2" 
        src="@/assets/sparkle_2.png"
      />
      <img 
        ref="sparkle3Ref" 
        class="coke-banner__sparkle-3" 
        src="@/assets/sparkle_2.png"
      />
    </div>
  </div>
</template>

<style scoped lang="scss">
@use './coke-banner.scss'
</style>