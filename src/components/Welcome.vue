<!--eslint-disable-->
<template>
  <div class="welcome container">
    <div class="card">
      <div class="card-content center-align">
        <div class="teal-text">
          <h2>Welcome</h2>
          <form @submit.prevent="enterChat">
            <label for="name">Enter your name:</label>
            <input type="text" name="name" v-model="name">
            <p v-if="feedback" class="red-text">{{ feedback }}</p>
            <button class="btn teal">Enter Chat</button>
        </form>
        </div>
        
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Welcome',
  data () {
    return {
      name: null,
      feedback: null,
    }
  },
  methods: {
    enterChat() {
      if (this.name) {
        this.$router.push({ name: 'Chat', params: { name: this.name } });
      } else {
        this.feedback = 'You must enter a name to join.';
      }
    },
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .welcome {
    max-width: 600px;
    margin-top: 100px;
  }
  .welcome h2 {
    font-size: 4em;
  }
</style>
