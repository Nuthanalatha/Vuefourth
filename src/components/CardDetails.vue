<template>
  <div @click="displayRecipe" class="card" style="width: 18rem">
    <div class="card-body">
      <h4>{{ id }}</h4>
      <h4>{{ name }}</h4>
      <img :src="img" class="card-img-top" alt="img" width="200" height="200" />
    </div>
  </div>

  <!-- <div>
    <div v-if="displayDetails" class="card1" style="width: 50rem">
      <div class="card-body">
        <h1>{{ name }}</h1>
        <img
          :src="img"
          class="card-img-top"
          alt="img"
          height="400"
          width="700"
        />
      </div>
      <h4>{{ steps }}</h4>
      <p>{{ description }}</p>
    </div> -->
  <!-- </div> -->
</template>

<script>
export default {
  emits: ["toggleRecipeStatus"],
  props: {
    id: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    img: {
      type: Image,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    steps: {
      type: String,
      required: true,
    },
  },

  // data() {
  //   return {
  //     displayDetails: false,
  //   };
  // },
  methods: {
    displayRecipe() {
      // this.displayDetails = !this.displayDetails;
      this.$emit("toggleRecipeStatus", this.id);
    },
  },
};
</script>

<style>
li {
  list-style-type: none;
}
/* .card1 {
  position: absolute;
  top: 70px;
  right: 200px;
  margin-top: 0;
} */
.flex-box {
  display: flex;
}
. {
  flex: 0.2;
  display: flex;
  flex-direction: column;
  margin-left: 5%;
}
</style>
