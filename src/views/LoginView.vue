<template>
  <div class="container mt-5">
    <div class="row justify-content-center">
      <div class="col-md-6">
        <div class="card">
          <div class="card-header">Login</div>
          <div class="card-body">
            <form action="" @submit="login">
              <div class="form-group">
                <label for="username">사용자 이름 : </label>
                <input type="text" class="form-control" id="username" v-model="username" required>
              </div>
              <div class="form-group">
                <label for="password">비밀번호 : </label>
                <input type="text" class="form-control" id="password" v-model="password" required>
              </div>
              <button type="button" class="btn btn-primary" @click="login">Login</button>
              <p v-if="loginError" class="text-danger">{{ loginError }}</p>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'LoginView',
  components: {
    // 추가적으로 사용할 컴포넌트들을 등록합니다.
  },
  data() {
    return {
      // 컴포넌트의 데이터를 초기화합니다.
      username : '',
      password : '',
      loginError : '',
    };
  },
  methods: {
    // 컴포넌트에서 사용할 메서드를 정의합니다.
    login() {
      this.$store.commit('loginUser', {username : this.username, password : this.password});
      console.log('결과', this.$store.state.user);
      // 로그인 결과 처리
      if(this.$store.state.user === null){
        this.username = '';
        this.password = '';
        this.loginError = '아이디 또는 비밀번호가 올바르지 않습니다.';
      }
      else{
        // 로그인 성공시 페이지 이동 등의 처리
        this.$router.push('/');
      }
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