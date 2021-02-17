<template>
  <div id="app">
    <aside id="sidebar">
      <div class="logo">
        <nuxt-link to="/">
          <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/1c/DC_Comics_logo.png/600px-DC_Comics_logo.png" alt="Logo" width="50">
        </nuxt-link>
      </div>
      <nav>
        Menu
      </nav>
    </aside>
    <main>
      <div id="top">
        <div class="searchbar">
          <search-bar class="input"></search-bar>
        </div>
        <div class="avatar">
          <div class="img-avatar"></div>
        </div>
      </div>
      <div id="title">
        Teste de Título
      </div>
      <div id="content">
        <Nuxt />
      </div>
    </main>
  </div>
</template>

<script>
import SearchBar from '~/components/layout/SearchBar.vue'
export default {
  components: { SearchBar },

}
</script>

<style lang="scss" scoped>
#app{
  display: flex;
  background: #F5F5FB;
  width: 100vw;
  height: 100vh;

  aside#sidebar{
    background: white;
    width: 180px;
    height: 100vh;
    overflow-y: auto;
    overflow-x: hidden;
    box-sizing: border-box;

    .logo{
      display: flex;
      justify-content: center;
      margin-top: 50px;
      margin-bottom: 50px;
    }

    nav{
      padding-left: 40px;
    }
  }

  main{
    width: 100%;
    box-sizing: border-box;
    padding-left: 40px;
    padding-top: 30px;
    padding-right: 40px;

    #top{
      width: 100%;
      display: flex;

      .searchbar{
        width: 90%;
      }

      .avatar{
        width: 10%;
        display: flex;
        justify-content: flex-end;

        .img-avatar{
          background: #C4C4C4;
          width: 40px;
          height: 40px;
          border-radius: 50%;
        }
      }
    }

    #title{
      font-family: 'Inter', sans-serif;
      font-style: normal;
      font-weight: 600;
      font-size: 28px;
      line-height: 34px;
      padding-top: 30px;
      padding-bottom: 20px;
    }

    #content{}
  }
}
</style>
