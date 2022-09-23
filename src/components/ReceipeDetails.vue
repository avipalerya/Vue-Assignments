<template>
  <div v-if="thatReceipe" class="card" style="width: 32rem">
    <ul class="list-group list-group-flush">
      <li class="list-group-item bg-light">{{ name }}</li>
      <img
        :src="img"
        class="list-group-item"
        alt="..."
        width="480"
        height="480"
      />
      <li class="list-group-item">steps in making {{ name }}</li>
      <li class="list-group-item card-text">{{ desc }}</li>
    </ul>
  </div>
</template>

<script>
export default {
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
    thatReceipe: {
      required: true,
    },
  },
};
</script>

<style scoped>
.card {
  text-align: center;
  font-weight: bold;
  margin-left: 80px;
}
</style>
