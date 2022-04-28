<template>
  <div class="content-container">
    <div class="content">
      <div class="title_bar" data-v-be3178dc="">
        <strong data-v-be3178dc="">Product Page</strong>
        <a class="btn btn-primary" @click="showModal" href="javascript:void(0)"
          >ADD PRODUCT</a
        >
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
            v-for="(product, index) in productPerPage"
            :key="index"
            :product="product"
          ></product>
        </div>
      </div>
      <paging
        :productne="products"
        :pageSize="pageSize"
        :currentPage="currentPage"
        @changePage="changePage"
      ></paging>
      <Modal
        v-show="isModalVisible"
        :products="products"
        @close="closeModal"
        @add-product="addProduct"
      />
    </div>
  </div>
</template>

<script>
import Product from "./Product.vue";
import Modal from "./Modal.vue";
import Paging from "./Paging.vue";

export default {
  components: {
    Modal,
    Product,
    Paging,
  },

  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    },
    addProduct(e) {
      this.products.push(e);
    },
    changePage(currentPage) {
      this.currentPage = currentPage;
    },
  },
  computed: {
    productPerPage() {
      let begin = (this.currentPage - 1) * this.pageSize;
      let end = this.currentPage * this.pageSize;
      return this.products.slice(begin, end);
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
        {
          title: "Product 10",
          description: "Description",
          tags: ["tag 1", "tag 2"],
          link: "Deserunt anim",
        },
        
      ],
      pageSize: 6,
      currentPage: 1,
    };
  },
};
</script>

<style scoped>
.content {
  position: absolute;
  top: 64px;
  left: 288px;
  width: 1152px;
  height: 834px;
  background: #ffffffff;
  border-radius: 0px;
  box-shadow: 0px 2px 7px #333a47, 0px 0px 0px #333a47;
}
/* Container 5 */
.quiz-box {
  position: absolute;
  top: 92px;
  left: 88px;
  width: 1020px;
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

.btn {
  padding: 10px 18px;
  align-items: center;
  justify-content: center;
  font-family: Josefin Sans;
  font-size: 16px;
  line-height: 16px;
  border: none;
  border-radius: 6px;
  text-decoration: none;
}
.title_bar {
  display: flex;
  justify-content: space-between;
  margin: 20px 40px 0px 60px;
}
strong {
  font-size: 32px;
  line-height: 42px;
  color: #3a414d;
  font-weight: bold;
}
.btn-primary {
  color: #fff;
  background: #56b4b8;
}

.quiz-content {
  display: grid;
  grid-template-columns: auto auto;
}
</style>
