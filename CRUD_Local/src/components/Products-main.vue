<template>
  <div>
    <b-table-simple responsive>
      <b-thead>
        <b-tr>
          <b-th>ID </b-th>
          <b-th>Product Name </b-th>
          <b-th>Product Price</b-th>
          <b-th>Product Description </b-th>
          <b-th>Product Image </b-th>
          <b-th>
            <b-button variant="warning" @click="openAddModal">ADD</b-button>
          </b-th>
        </b-tr>
      </b-thead>
      <b-tbody>
        <b-tr v-for="product in products" :key="product.id">
          <b-td>{{ product._id }}</b-td>
          <b-td>{{ product.productName }}</b-td>
          <b-td>{{ product.productPrice }}</b-td>
          <b-td>{{ product.productDescription }}</b-td>
          <b-td>
            <img :src="product.productImageURL" width="220px" height="160px" />
          </b-td>
          <b-td>
            <b-button
              variant="primary"
              class="mx-2"
              @click="getSelectedProduct(product)"
              >EDIT</b-button
            >
            <b-button variant="danger" @click="removeProd(id)"
              >DELETE
            </b-button>
          </b-td>
        </b-tr>
      </b-tbody>
    </b-table-simple>

    <!-- add product component -->
    <add-product
      :showHideAddModal="showHideAddModal"
      @closeAddModal="closeAddModal"
      :products="products"
    />

    <edit-product
      :selectedProduct="selectedProduct"
      :showHideEditModal="showHideEditModal"
      @closeEditModal="closeEditModal"
    />
  </div>
</template>

<script>
import AddProduct from "../components/Add-product.vue";
import EditProduct from "./Edit-product.vue";
export default {
  components: { AddProduct, EditProduct },
  data() {
    return {
      products: [
        {
          productDescription: "yellow car",
          productImageURL:
            "https://imgd.aeplcdn.com/1056x594/cw/ec/21724/Audi-R8-Right-Front-Three-Quarter-66713.jpg?v=201711021421&q=75&wm=1",
          productName: "Audi R8",
          productPrice: 30000000,
          _id: 1,
        },
        {
          productDescription: "iPhone 12",
          productImageURL:
            "https://store.storeimages.cdn-apple.com/4668/as-images.apple.com/is/iphone-12-mini-purple-witb-2021?wid=142&hei=340&fmt=jpeg&qlt=95&.v=1617138139000",
          productName: "Better Quality",
          productPrice: 50000,
          _id: 2,
        },
        {
          productDescription:
            "Nike Air More Uptempo  '96 brings classic basketball back to the streets",
          productImageURL:
            "https://static.nike.com/a/images/t_PDP_864_v1/f_auto,b_rgb:f5f5f5/2fa25188-aadc-4bbf-8e52-3a96f0586ad3/air-more-uptempo-96-shoes-33Qdlb.png",
          productName: "The Nike Air More Uptempo ",
          productPrice: 20000,
          _id: 3,
        },
      ],
      selectedProduct: {},
      showHideAddModal: false,
      showHideEditModal: false,
    };
  },
  methods: {
    // open add modal
    openAddModal() {
      this.showHideAddModal = true;
    },
    // close add modal
    closeAddModal() {
      this.showHideAddModal = false;
    },

    // open edit modal
    openEditModal() {
      this.showHideEditModal = true;
    },
    //close edit modal
    closeEditModal() {
      this.showHideEditModal = false;
    },
    //getting the selected product on click of edit
    getSelectedProduct(prod) {
      this.selectedProduct = prod;
      this.openEditModal();
      console.log("selected prod", prod);
    },

    removeProd(ID) {
      console.log("products deleted is :", this.products[ID]);
      this.products.splice(ID, 1);
      //   this.products.filter((product) => product._id === ID);
      //   console.log(ID);
    },
  },
};
</script>

<style></style>
