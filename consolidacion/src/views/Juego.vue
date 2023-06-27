<template>

  <div class="container">
    <div v-if="game != null" class="card" >
      <img :src="game.background_image" class="card-img-top" alt="..." />
      <div class="card-body">
        <h5 class="card-title">{{ game.name }}</h5>
        <p class="card-text">
          {{ game.description_raw }}
        </p>
      </div>
      <ul class="list-group list-group-flush">
        <li class="list-group-item">Clasificación: {{ game.rating }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "component-name",
  props: {
    id: {
      type: String,
      required: true,
    },
  },
  data: function () {
    return {
      game: null,
    };
  },
  // computed: {},
  methods: {
    getData() {
      axios
        .get(
          `https://api.rawg.io/api/games/${this.id}?key=de294bb09054413cb1d75970171acf08`
        )
        .then((data) => {
          this.game = data.data;
        });
    },
  },

  // watch: {},
  // components: {},
  // mixins: [],
  // filters: {},
  // -- Lifecycle Methods
  created() {
    this.getData();
  },
  // -- End Lifecycle Methods
};
</script>

<style scoped>
.container {
  width:60%;
  margin: 0 auto;
}
</style>