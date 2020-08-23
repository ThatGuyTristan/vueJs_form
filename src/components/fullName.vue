<template>
  <div>
    <div id="firstName">
      <label for="firstName"> First Name </label>
        <input type="text" @change="sendName" v-model="firstName">
    </div>

    <div id="middleInitial">
      <label for="firstName"> Middle Initial </label>
        <input type="text" @change="sendName" v-model="middleInitial" rows="4">
    </div>

    <div id="lastName">
      <label for="firstName"> Last Name </label>
        <input type="text" @change="sendName" v-model="lastName">
    </div>
  </div>
</template>

<script>
export default {
  data (){
    return {
      firstName: "",
      middleInitial: "",
      lastName: ""
    }
  },
  methods: {
    sendName(){
      const fullName = `${this.firstName} ${this.middleInitial} ${this.lastName}`;
      this.$emit('input', fullName)
    }
  }
}
</script>
