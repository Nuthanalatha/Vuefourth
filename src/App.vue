<template>
  <h1 class="container border mb-3">SLV Recipe book</h1>
  <ul>
    <card-details
      v-for="dish in dishes"
      :key="dish.id"
      :id="dish.id"
      :name="dish.name"
      :img="dish.img"
      :description="dish.description"
      :steps="dish.steps"
      @toggleRecipeStatus="toggleRecipeStatus"
    />
  </ul>
  <display-details
    v-for="dish in dishes"
    :key="dish.id"
    :name="dish.name"
    :description="dish.description"
    :id="dish.id"
    :img="dish.img"
    :show="dish.showRecipe"
  />
</template>

<script>
import CardDetails from "./components/CardDetails.vue";
import DisplayDetails from "./components/DisplayDetails.vue";

export default {
  name: "App",
  components: {
    CardDetails,
    DisplayDetails,
  },
  data() {
    return {
      dishes: [
        {
          id: 1,
          name: "Gulab Jamun",
          img: "https://media.istockphoto.com/photos/gulab-jamun-picture-id668147754?b=1&k=20&m=668147754&s=170667a&w=0&h=mvPHOcBx-Rce1DsEgqz4JhCSVckxcwRle82lI_NCKVo=",
          description:
            "Boil sugar and water to prepare syrup remove from fire; add cardamom and keep aside to cool.In a mixing bowl put the flour, paneer, sooji, Nestlé MILKMAID , baking powder and baking soda. Mix gently to make a soft dough, do not knead too much.Divide the mixture into 30-35 portions and gently roll into round gulab jamuns. Fry in the oil at very low flame till golden brown in color.Keep putting the fried gulab jamuns in the prepared sugar syrup, once all the gulab jamuns are in the sugar syrup bring it to a boil and remove from flame.Serve warm.",
          steps: "Steps in making Gulab Jamun",
          showRecipe: false,
        },
        {
          id: 2,
          name: "Paneer Tikka",
          img: "https://media.istockphoto.com/photos/paneer-tikka-served-with-sauces-picture-id1256834391?b=1&k=20&m=1256834391&s=170667a&w=0&h=pXvkzYwNMdpyHKwHlg4UxzhGx8TBnkNiLMYQv3d069g=",
          description:
            "First, cut about six or more pieces of paneer and some capsicum, onion and tomato for the recipe. Once all the fresh ingredients are nicely diced, it’s time to prepare the masala.To prepare the masala, take a bowl and add two tablespoons hung curd, 1 tablespoon ginger garlic paste, 1 tablespoon Degi Mirch, half tablespoon salt, some black salt, 1 tablespoon garam masala, 1 tablespoon kitchen king, 2 tablespoon mustard oil, and 1 tablespoon green chilli paste for a spicy flavour. Now, mix all these ingredients well to make a thick paste.Now add diced paneer cubes and vegetables (capsicum, large tomato and large onion) to the prepared masala. Mix everything well with hands to ensure paneer and veggies are coated with masala properly.Cover the bowl and keep the ingredients in the fridge for about five to six minutes. This step is important to ensure that the vegetables and paneer absorb as much masala as possible.After five minutes, it’s time to put paneer and vegetables on skewers. Gently put the ingredients without tearing them off completely. Now put the skewer into a hot tandoor and leave it for 10 minutes. When the cubes are reddish-brown, the dish is ready to be served.Now it’s time to take out paneer tikka on the plate. Don’t put them directly on paper tissues because the heat and moisture content from paneer cubes can easily stick to paper tissues. So, always put them on the plate directly. Garnish it a little for presentation with lachha onion, lemon slice and some fresh coriander leaves. Now the paneer tikka is all ready to be served or eaten hot. You can enjoy it using simple toothpicks or a fork, depending on what your guests prefer. ",
          steps: "Steps in making Paneer Tikka",
          showRecipe: false,
        },
        {
          id: 3,
          name: "Veg Pulao",
          img: "https://media.istockphoto.com/photos/delicious-veg-peas-pulao-rice-picture-id1273291313?b=1&k=20&m=1273291313&s=170667a&w=0&h=yyPz8BHHjvLOTdzE3ZewYRrAPZCqgTUvZGkxHeBT-QA=",
          description:
            "firstly, in a small mixi take ½ cup coriander, ¼ cup mint, 1 inch ginger, 2 clove garlic, 2 chilli, 2 pod cardamom, 1 inch cinnamon, 5 cloves and 1 tsp fennel.add ¼ cup water and blend smooth paste. keep aside.ina large kadai, heat 2 tbsp ghee. add 1 tsp cumin, 1 bay leaf, 1 inch cinnamon, 2 pod cardamom, 3 cloves, ½ tsp pepper and 5 cashew.saute on low flame until the spices turn aromatic.now add ½ onion and saute until the colour changes slightly.further, add 1 tomato and saute until the tomatoes turn soft and mushy.additionally, add 5 beans, ½ capsicum, 2 tbsp peas, ½ carrot and ½ potato.saute for a minute until the vegetables turn aromatic.now add prepared coriander pudina masala paste and 1 tsp salt. mix well.further, add 2 cup water and stir well getting to a boil.once the water comes to a rolling boil, add 1 cup basmati rice. make sure to soak basmati rice for 20 minutes.mix well, cover and simmer for 20 minutes.after 20 minutes, veg pulao is ready to serve.",
          steps: "Steps in making Veg Pulao",
          showRecipe: false,
        },
      ],
    };
  },
  methods: {
    // getDisplayDetails(showRecipe){
    //   this.userShowRecipe = showRecipe;
    toggleRecipeStatus(recipeID) {
      let identifiedRecipe = this.dishes.find((dish) => dish.id === recipeID);
      identifiedRecipe.showRecipe = !identifiedRecipe.showRecipe;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
.container {
  background-color: green;
  color: aliceblue;
  padding: 20px;
  margin-top: 0px;
}
.flex-box {
  display: flex;
}
</style>
