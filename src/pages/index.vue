<script setup lang="ts">
defineOptions({
  name: 'IndexPage',
})
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
function go() {
  if (name)
    router.push(`/hi/${encodeURIComponent(name)}`)
}

const { t } = useI18n()
</script>

<template>
  <div>
    <div text-4xl>
      🜾
    </div>
    <p>
      <a rel="noreferrer" href="https://github.com/BBuchholz/worthy-mountain" target="_blank">
        Worthy Mountain
      </a>
    </p>
    <p>
      <em text-sm opacity-75>base template for all Coventry Grove Projeckts</em>
    </p>

    <div py-4 />

    <TheInput
      v-model="name"
      placeholder="enter myrKi..."
      autocomplete="false"
      @keydown.enter="go"
    />
    <label class="hidden" for="input">We require more than a mere key for entry...</label>

    <div>
      <button
        m-3 text-sm btn
        :disabled="!name"
        @click="go"
      >
        {{ t('button.go') }}
      </button>
    </div>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
