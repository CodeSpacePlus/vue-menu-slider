<template>
  <div class="modal-container" v-bind:class="{ 'show-modal': toggleModal }">
    <div class="modal">
      <button class="close-btn" @click="toggleForm">
        <i class="fa fa-times"></i>
      </button>
      <div class="modal-header">
        <h3>Sign Up</h3>
      </div>
      <div class="modal-content">
        <strong>Register with us to get offers, support, and more</strong>
        <form class="modal-form" @submit="submitForm">
          <div>
            <label for="name">Name</label>
            <input
              v-model="name"
              type="text"
              class="form-input"
              placeholder="Enter Name"
            />
          </div>
          <div>
            <label for="Email">Email</label>
            <input
              v-model="email"
              type="text"
              class="form-input"
              placeholder="Enter Email"
            />
          </div>
          <div>
            <label for="Password">Password</label>
            <input
              v-model="password"
              type="password"
              class="form-input"
              placeholder="Enter Password"
            />
          </div>
          <div>
            <label for="Password_Confirm">Confirm Password</label>
            <input
              v-model="password_confirm"
              type="password"
              class="form-input"
              placeholder="Confirm Password"
            />
          </div>
          <input type="submit" value="submit" class="submit-btn" />
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Modal',
  props: ['toggle'],
  data() {
    return {
      name: '',
      email: '',
      password: '',
      password_confirm: '',
    };
  },
  methods: {
    toggleForm() {
      this.$emit('close-modal');
    },
    submitForm(e) {
      e.preventDefault();
      this.toggleForm();
    },
  },
  computed: {
    toggleModal() {
      return this.toggle;
    },
  },
};
</script>

<style scoped>
.modal-container {
  background-color: rgba(0, 0, 0, 0.6);
  display: none;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.modal-container.show-modal {
  display: block;
}

.modal {
  background-color: #fff;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  position: absolute;
  overflow: hidden;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  max-width: 100%;
  width: 400px;
  animation-name: modalopen;
  animation-duration: var(--modal-duration);
}

.modal-header {
  background-color: var(--primary-color);
  color: #fff;
  padding: 15px;
}

.modal-header h3 {
  margin: 0;
}

.modal-content {
  padding: 20px;
}

.modal-form div {
  margin: 15px 0;
}

.modal-form label {
  display: block;
  margin-bottom: 5px;
}

.modal-form .form-input {
  padding: 8px;
  width: 100%;
}

.close-btn {
  background-color: transparent;
  font-size: 25px;
  position: absolute;
  top: 0;
  right: 0;
}

@keyframes modalopen {
  from {
    opacity: 0;
  }

  to {
    opacity: 1;
  }
}
</style>
