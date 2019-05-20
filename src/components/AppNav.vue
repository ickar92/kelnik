<template>
  <ul class="app-nav">
    <li
      v-for="(navItem, index) of navData"
      :key="index"
      class="nav-item"
      :to="navItem.to"
      @click="onNavItemClick(navItem)"
    >
      {{ navItem.text }}
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      navData: [
        {
          text: 'Объекты',
          to: { name: 'home' },
        },
        {
          text: 'Компания',
          to: { name: 'objects' },
        },
        {
          text: 'Как купить',
          to: { name: 'about' },
        },
      ],
    };
  },

  methods: {
    onNavItemClick(navItem) {
      this.$router.push(navItem.to);
    },
  },
};
</script>

<style lang="scss" scoped>
.app-nav {
  height: 126px;
  background: #002f2f;
  color: #fefefe;
  font-family: "Open Sans";
  margin: 0;
  padding: 0;
  list-style: none;
  display: flex;
  justify-content: center;
}

.nav-item {
  color: white;
  text-decoration: none;
  font-size: 24px;
  font-weight: 400;
  padding: 15px;
  cursor: pointer;
}
</style>
