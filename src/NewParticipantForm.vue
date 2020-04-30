<template>

    <form @submit.prevent="add()" class="form-group col-sm-3 my-1">
     <label>Firstname</label>
      <input  class="form-control mb-2" type="text" v-model ="newParticipant.firstname"><br>
      <label>Lastname</label>
      <input class="form-control mb-2" type="text" v-model ="newParticipant.lastname"><br>
      <button class="btn btn-primary">Add new participant</button>
    </form>

</template>

<script>
  export default {
    data() {
      return {newParticipant: {}};
    },
    methods: {
      add() {
        this.$emit('added', this.newParticipant);
        this.newParticipant = {};
      }
    }
  };
</script>