<template>
  <div id="app" class="app" v-bind:class="{ 'show-nav': showNav }">
    <Navigator />
    <Header @toggle-modal="toggleModal" @toggle-nav="toggleNav" />
    <Body />
    <Modal v-bind:toggle="toggle" @close-modal="toggleModal" />
  </div>
</template>

<script>
import Navigator from './components/Navigator';
import Header from './components/Header';
import Body from './components/Body';
import Modal from './components/Modal';

export default {
  name: 'App',
  data() {
    return {
      toggle: false,
      showNav: false,
    };
  },
  components: {
    Navigator,
    Header,
    Body,
    Modal,
  },
  methods: {
    toggleModal() {
      this.toggle = !this.toggle;
    },
    toggleNav() {
      this.showNav = !this.showNav;
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Lato&display=swap');

:root {
  --modal-duration: 1s;
  --primary-color: #30336b;
  --secondary-color: #be22dd;
}

* {
  box-sizing: border-box;
}

body {
  font-family: 'Lato', sans-serif;
  margin: 0;
  transition: transform 0.3s ease;
}

.app.show-nav {
  transform: translateX(200px);
}

button,
input[type='submit'] {
  background-color: var(--secondary-color);
  border: 0;
  border-radius: 5px;
  color: #fff;
  cursor: pointer;
  padding: 8px 12px;
}
</style>
