<template>
  <div class="layout">
    <nav class="nav">
      <NuxtLink class="link" :class="{ current: currentSelected('/') }" to="/">
        Home
      </NuxtLink>
      <NuxtLink
        class="link"
        :class="{ current: currentSelected('/categories') }"
        to="/categories"
      >
        Categories
      </NuxtLink>
    </nav>
    <slot />
  </div>
</template>

<script lang="ts" setup>
const router = useRoute();
const currentSelected = (path: string) => {
  return router.path === path;
};
</script>

<style lang="scss">
@use "@/assets/styles/colors.scss" as colors;

.layout {
  width: 620px;
  margin: 0px auto 50px;
}

.nav {
  margin-top: 10px;
  margin-bottom: 30px;
  position: relative;

  .link {
    color: colors.$green-medium;
    display: inline-block;
    font-size: 14pt;
    margin-right: 20px;

    &.current {
      text-decoration: underline;
      color: colors.$green-light;
      pointer-events: none;
    }
  }

  .link:hover {
    color: colors.$green-light;
  }
}
</style>
