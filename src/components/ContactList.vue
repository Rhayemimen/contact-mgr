<template>
  <div>
    <h1><fa-icon icon="address-book"></fa-icon> Contact List</h1>
    <div class="row" @mouseleave="detailSelect = null">
      <div class="col-6">
        <ul class="list-group">
          <li
            v-for="contact in contactsList"
            v-bind:key="contact.id"
            class="list-group-item"
            @mouseover="detailSelect = contact"
          >
          <fa-icon icon="user"></fa-icon> {{ contact.name }}
          </li>
        </ul>
      </div>
      <div class="col-6">
        <Detail v-if="detailSelect != null" v-bind:contact="detailSelect"></Detail>
      </div > 
    </div>
  </div>
</template>

<script>
import Detail from "@/components/Detail.vue";

export default {
  name: "ContactList",
  components: { Detail },
  props: {
    contactsList:Array
  },
  data() {
    return {
      detailSelect: null,
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
