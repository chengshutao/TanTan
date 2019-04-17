<template>
  <header class="mint-header">
    <div class="mint-header-button is-left">
      <a href="/" class="router-link-active">
        <button class="mint-button mint-button--default mint-button--normal">
          <!---->
          <label class="mint-button-text">
            <div class="menu">
              <p></p>
              <p></p>
              <p></p>
            </div>
          </label>
        </button>
      </a>
    </div>
    <h1 class="mint-header-title" v-text="headerTitle"></h1>
    <div class="mint-header-button is-right" v-text="headerRight"></div>
  </header>
</template>
<script>
export default {
  data() {
    return {
      headerTitle: "吹挚友",
      headerRight: "编辑"
    };
  }
};
</script>
<style scoped>
.mint-header {
  background: #c85640;
  font-size: 0.426667rem;
  position: fixed;
  width: 100%;
  height: 1.066667rem;
  top: 0;

  z-index: 99;
}
.menu {
  display: flex;
  height: 0.506667rem;
  flex-direction: column;
  justify-content: space-between;
}
.menu p {
  width: 0.506667rem;
  height: 0.026667rem;
  background: #fff;
}
</style>

