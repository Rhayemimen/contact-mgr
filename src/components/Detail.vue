<template>
    <div class="card h-100">
      <h2> <fa-icon icon="user"></fa-icon> {{contact.name}}</h2>
      <div class="card-body">
        <p class="card-text"><fa-icon icon="at"></fa-icon> {{contact.email}}</p>
        <p class="card-text"><fa-icon icon="phone-square-alt"></fa-icon> {{contact.phone}}</p>
        <p class="card-text"><fa-icon icon="map"></fa-icon> {{contact.address.street}} {{contact.address.city}}</p>
      </div>
  </div>
</template>

<script>

export default {
    name: "Detail",
    props: {
        contact:Object
    }
}
</script>

<style>

</style>