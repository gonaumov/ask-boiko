<template>
  <div>
    {{ $t("changeLanguage") }}:
    <a v-if="$i18n.locale != 'en'" @click="$i18n.locale = 'en'" href="#">English</a>
    <a v-if="$i18n.locale != 'tr'" @click="$i18n.locale = 'tr'" href="#">Türk</a>
    <a v-if="$i18n.locale != 'bg'" @click="$i18n.locale = 'bg'" href="#">Български</a>
  </div>
</template>

<style lang="scss" scoped>
  a {
    margin: 5px;
  }
</style>
