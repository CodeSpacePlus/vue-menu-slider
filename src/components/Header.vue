<template>
  <div>
    <header>
      <button class="toggle" @click="$emit('toggle-nav')">
        <i class="fa fa-bars fa-2x"></i>
      </button>

      <h1>My Landing Page</h1>

      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Reprehenderit,
        voluptates.
      </p>

      <button class="cta-btn" @click="$emit('toggle-modal')">
        Sign Up
      </button>
    </header>
  </div>
</template>

<script>
export default {
  name: 'Header',
};
</script>

<style scoped>
header {
  background-color: var(--primary-color);
  color: #fff;
  font-size: 130%;
  position: relative;
  padding: 40px 15px;
  text-align: center;
}

header h1 {
  margin: 0;
}

header p {
  margin: 30px 0;
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

button:focus {
  outline: none;
}

.toggle {
  background-color: rgba(0, 0, 0, 0.3);
  position: absolute;
  top: 20px;
  left: 20px;
}

.cta-btn {
  padding: 12px 30px;
  font-size: 20px;
}
</style>
