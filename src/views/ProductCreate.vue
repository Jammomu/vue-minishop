<template>
  <div class="">
    <h1>상품등록하기</h1>
    <form>
      <div>
        <label for="">상품명 : <input type="text" v-model="newProduct.product_name" id="name"></label>
      </div>
      <div>
        <label for="">가격 : <input type="text" v-model="newProduct.product_price" id="price"></label>
      </div>
      <div>
        <label for="">이미지 : <input type="text" v-model="newProduct.path" id="path"></label>
      </div>
      <div>
        <label for="">카테고리1 : 
          <select v-model="newProduct.category1" id="category1">
            <option value="">선택하세요</option>
            <option value="전자기기">전자기기</option>
            <option value="액세서리">액세서리</option>
          </select>
        </label>
      </div>
      <div>
        <label for="">카테고리2 : 
          <select v-model="newProduct.category2" id="category2">
            <option value="">선택하세요</option>
            <option value="노트북">노트북</option>
            <option value="모니터">모니터</option>
            <option value="PC용품">PC용품</option>
          </select>
        </label>
      </div>
      <div>
        <label for="">카테고리3 : 
          <select v-model="newProduct.category3" id="category3">
            <option value="">선택하세요</option>
            <option value="게이밍">게이밍</option>
            <option value="무선">무선</option>
          </select>
        </label>
      </div>
      <button type="text" class="btn btn-primary" @click="addGood">상품 등록</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'ProductCreate',
  data() {
    return {
      newProduct : {
        product_name : '',
        product_price : 0,
        path : 'none.jpg',
        category1 : '',
        category2 : '',
        category3 : '',

      }
    };
  },
  watch: {
    // 데이터를 감시하고 처리할 로직을 작성합니다.
    // sample1() {
    //   console.log('');
    // }
  },
  computed: {
    // 필요한 계산된 속성을 정의합니다.
    // sample2() {
    //   return '';
    // }
  },
  methods: {
    addGood(){
      this.$store.commit('addProduct', this.newProduct);
      this.$router.push('/sales');
    }
  },
  setup() {
    // Vue 3 Composition API의 setup 함수에서 추가적인 로직을 처리할 수 있습니다.
  },
  created() {
    // 컴포넌트가 생성될 때 실행될 로직을 작성합니다.
  },
  mounted() {
    // 컴포넌트가 DOM에 마운트된 직후 실행될 로직을 작성합니다.
  },
  unmounted() {
    // 컴포넌트가 파괴되기 전 실행될 로직을 작성합니다.
  }
};
</script>

<style scoped>
/* 스타일을 추가하세요 */
</style>