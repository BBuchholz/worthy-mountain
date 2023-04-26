<script setup lang="ts">
const {
  t,
  // locale,
} = useI18n()

// async function toggleLocales() {
//   // change to some real logic
//   const locales = availableLocales
//   const newLocale = locales[(locales.indexOf(locale.value) + 1) % locales.length]
//   await loadLanguageAsync(newLocale)
//   locale.value = newLocale
// }
</script>

<template>
  <nav flex="~ gap-4" mt-6 justify-center text-xl>
    <RouterLink icon-btn to="/" :title="t('button.home')">
      🜾
    </RouterLink>

    <button icon-btn :title="t('button.toggle_dark')" @click="toggleDark()">
      <div i="carbon-sun dark:carbon-moon" />
    </button>

    <RouterLink icon-btn to="/zhones" :title="t('button.toggle_langs')">
      <div i-carbon-language />
    </RouterLink>

    <RouterLink icon-btn to="/about" :title="t('button.about')">
      <div i-carbon-dicom-overlay />
    </RouterLink>

    <RouterLink icon-btn rel="noreferrer" to="/stream" title="Stream">
      <div i-carbon-events />
    </RouterLink>
  </nav>
</template>
