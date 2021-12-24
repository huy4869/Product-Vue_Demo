<template>
  <div class="content-container">
    <div class="content">
      <div class="header-menu-item" @click="showModal">
        Create
        <svg class="arrow-icon"></svg>
      </div>
      <div class="quiz-box">
        <div class="quiz-content">
          <!-- Which of the following(s) is/are the nicknames of version(s) of
          android? <br />
          1)cupcake <br />
          2) muffin <br />
          3)honeycomb <br />
          4)gingerbread <br />
          <br />
          a. 1,2,3 <br />
          b. 2,3,4 <br />
          c. 1,3,4 <br />
          d. 1,2,4 <br />

          <nav>
            <div class="menu-item">
              <a href=""></a><a href=""></a><a href=""></a>
            </div>
          </nav> -->
          <product
            v-for="(product, index) in products"
            :key="index"
            :product="product"
          ></product>
          <Modal v-show="isModalVisible" :products="products" @close="closeModal" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Product from "./Product.vue";
import Modal from "./Modal.vue";

export default {
  components: { Modal, Product },

  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
  },
  data() {
    return {
      isModalVisible: false,

      products: [
        {
          title: "Product 1",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        {
          title: "Product 2",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        {
          title: "Product 3",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        {
          title: "Product 4",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        {
          title: "Product 5",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        {
          title: "Product 6",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        {
          title: "Product 7",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        {
          title: "Product 8",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        {
          title: "Product 9",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
      ],
    };
  },
};
</script>

<style scoped>
.content {
  position: absolute;
  top: 62px;
  left: 288px;
  width: 1152px;
  height: 836px;
  background: #ffffffff;
  border-radius: 0px;
  box-shadow: 0px 2px 11px #333a47, 0px 0px 2px #333a47;
}
/* Container 5 */
.quiz-box {
  position: absolute;
  top: 72px;
  left: 88px;
  width: 960px;
  height: 614px;
  background: #ffffffff;
  border-radius: 6px;
  box-shadow: 0px 2px 11px #333a47, 0px 0px 2px #333a47;
}

/* Text 11 */
.quiz-content {
  position: absolute;
  top: 59px;
  left: 81px;
  width: 802px;
  height: 503px;
  font-family: Epilogue;
  font-size: 22px;
  line-height: 34px;
  color: #21262eff;
}
</style>
