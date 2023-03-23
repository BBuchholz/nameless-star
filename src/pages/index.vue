<script setup lang="ts">
defineOptions({
  name: 'IndexPage',
})
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name)
    router.push(`/hi/${encodeURIComponent(name)}`)
}

const { t } = useI18n()
</script>

<template>
  <div>
    <!-- <div text-4xl>
      <div i-carbon-campsite inline-block />
    </div> -->
    <!-- <div>
      <img src="./sonic-circle-pic.jpg" alt="image of musicians around a fire">
    </div> -->
    <p>
      <a rel="noreferrer" href="https://github.com/BBuchholz/nameless-star" target="_blank">
        Sonic Circle
      </a>
    </p>
    <p>
      <em text-sm opacity-75>{{ t('intro.desc') }}</em>
    </p>
    <p>---</p>
    <p class="text-2xl">
      <a href="https://anxious-grove.netlify.app/">One of the MyriaD sites...</a>
    </p>
    <p>---</p>
    <p class="text-4xl">
      <a href="mailto:soniccirclesoundingboard@gmail.com?subject=Sonic%20Circle%20Idea%20Submission&body=uuid%3A%20REPLACE_THIS%0AcreatedAt%3A%20REPLACE_THIS%0A%0A---%20above%20this%20line%20is%20for%20internal%20purposes%2C%20add%20your%20idea%20below---%0A%0A">SUBMIT AN IDEA</a>
    </p>
    <p>---</p>
    <RouterLink class="text-2xl -mb-6 m-auto" to="/agile" :title="t('button.agile')">
      <p>What's next? (click me)</p>
    </RouterLink>
    <p>---</p>
    <RouterLink class="text-2xl -mb-6 m-auto" to="/sc-portfolios" :title="t('button.to-do')">
      <p>Portfolios (click me)</p>
    </RouterLink>
    <p>---</p>
    <p>FUCK WITH THE STYLING (make all this prettier, I'm thinking IdeaComponent.vue or something to abstract the component)</p>
    <p>---</p>
    <RouterLink class="text-2xl -mb-6 m-auto" to="/to-do" :title="t('button.to-do')">
      <p>To Do (click me)</p>
    </RouterLink>
    <p>---</p>
    <p>setup "rounds" wherein you have anywhere between 1 and 4 Pomodoro sessions to do something to a mix and submit within a week, with your logged sessions to give credit for pragmatic expediency on the one hand and also patient devotion in the other, in this way participants earn placements within vector spaces of correlation (through commonality of medium)</p>
    <p>---</p>
    <p>use kits as first round starters (eg. "build a loop with this kit to be used by another participant in the next round(you will be swapping so try to keep it rhythmic :) )</p>
    <div py-4 />

    <TheInput
      v-model="name"
      placeholder="What's your name?"
      autocomplete="false"
      @keydown.enter="go"
    />
    <label class="hidden" for="input">{{ t('intro.whats-your-name') }}</label>

    <div>
      <button
        btn m-3 text-sm
        :disabled="!name"
        @click="go"
      >
        {{ t('button.go') }}
      </button>
    </div>
    <div>
      <img src="./sonic-circle-pic.jpg" alt="image of musicians around a fire">
    </div>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>

<style>
ul {
  list-style: circle;
}
</style>
