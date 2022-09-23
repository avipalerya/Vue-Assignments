<template>
  <nav-bar />
  <div class="flexbox">
    <div>
      <receipe-book
        v-for="receipe in receipes"
        :key="receipe.id"
        :name="receipe.name"
        :img="receipe.img"
        :desc="receipe.desc"
        :id="receipe.id"
        @receipeStatus="receipeStatus"
      />
    </div>
    <div>
      <receipe-details
        v-for="receipe in receipes"
        :key="receipe.id"
        :name="receipe.name"
        :img="receipe.img"
        :desc="receipe.desc"
        :id="receipe.id"
        :thatReceipe="receipe.thatReceipe"
      />
    </div>
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import ReceipeBook from "./components/ReceipeBook.vue";
import ReceipeDetails from "./components/ReceipeDetails.vue";
export default {
  name: "App",
  components: { ReceipeBook, NavBar, ReceipeDetails },
  data() {
    return {
      receipes: [
        {
          id: 1,
          name: "Instant No Yeast Naan",
          desc: "This improvised meal shows how incorporating a few Indian ingredients into your meals can make them a little more exciting. Mango chutney and curry powder bring to life a simple dish of sautéed shrimp and rice in this Indian food recipe. (via Masala & Meatballs; photo via Alanna Taylor-Tobin)",
          img: "https://www.brit.co/media-library/instant-no-yeast-naan.jpg?id=22867003&width=800&height=1066&coordinates=0%2C0%2C146%2C0&quality=80",
        },
        {
          id: 2,
          name: "Veggie-Loaded Butter Chicken Curry",
          desc: "This lightened up butter chicken curry relies on yogurt instead of coconut cream to make a luscious sauce, and it’s loaded with extra veggies for added nutrients and fiber. (via Drizzle and Dip)",
          img: "https://www.brit.co/media-library/veggie-loaded-butter-chicken-curry-in-a-top-indian-food-recipe.jpg?id=22867005&width=800&height=1066&coordinates=0%2C23%2C0%2C0&quality=80",
        },
        {
          id: 3,
          name: "Dal Bati Churma",
          desc: "One of the most famous dishes from the state, no Rajasthani food is complete without D al Bati Churma. The round B atis dipped in ghee with Panchkuti dal and c hurma make for an appetizing combination",
          img: "https://wp.scoopwhoop.com/wp-content/uploads/2014/09/5677315b6e510a6f3a759a81_1.jpg",
        },
        {
          id: 4,
          name: " Mysore Masala Dosa",
          desc: "The heart throb of Karnataka food. This one is well-traveled across the world and is most loved for its delicate and exquisite flavours. A crisp dosa, quite similar to the regular masala dosa but with a twist of fiery red chutney.",
          img: "https://t4.ftcdn.net/jpg/01/89/45/21/360_F_189452136_gJBG4ZRXY9NnZZCGV2s8QhObmpeerJTO.jpg",
        },
      ],
    };
  },
  methods: {
    receipeStatus(receipeID) {
      console.log("receipeID from child to parent", receipeID);
      let identifiedReceipe = this.receipes.find(
        (receipe) => receipe.id === receipeID
      );
      console.log("identifiedReceipe", identifiedReceipe);
      identifiedReceipe.thatReceipe = !identifiedReceipe.thatReceipe;
    },
  },
};
</script>

<style>
.flexbox {
  display: flex;
}
</style>
