<template>
  <div class="form-group">
    <div class="form-group col-md-6">
      <h1>Participants list</h1>
      <participants-list :list="participants"></participants-list>
    </div>

    <h3 class="form-group col-md-6" >New participant</h3>
    <new-participant-form @added="addNewParticipant($event)"></new-participant-form>
  </div>
</template>

<script>
  import NewParticipantForm from "./NewParticipantForm.vue";
  import ParticipantsList from './ParticipantsList.vue';

  export default {
    components: {NewParticipantForm, ParticipantsList},
    
    data() {
      return {
         participants:[
            {firstname:"John", lastname:"Doe"},
            {firstname:"Robin", lastname:"Hood"},
            {firstname:"Chuck", lastname:"Norris"},
            {firstname:"Kate", lastname:"Flower"},
          ],
      };
    },
    methods: {
      addNewParticipant(newParticipant) {
        this.participants.push(newParticipant);
      }
    }
  };
</script>