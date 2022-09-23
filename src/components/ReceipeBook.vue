<template>
  <div @click="toggleDetails" class="card" style="width: 19rem">
    <ul class="list-group list-group-flush">
      <li class="list-group-item">{{ id }}</li>
      <li class="list-group-item">{{ name }}</li>
      <img
        :src="img"
        class="list-group-item"
        alt="..."
        width="300"
        height="300"
      />
    </ul>
  </div>
</template>

<script>
export default {
  emits: ["receipeStatus"],
  components: {},
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
      required: true,
    },
    desc: {
      type: String,
      required: true,
    },
  },
  methods: {
    toggleDetails() {
      this.$emit("receipeStatus", this.id);
    },
  },
};
</script>

<style scoped>
.card {
  text-align: center;
  font-weight: bold;
}
</style>
