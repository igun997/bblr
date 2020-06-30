<template>
  <f7-app>
    <f7-appbar title="Admin">
      <div class="left">
        <f7-button icon-color="white" small panel-toggle="left" class="display-flex " icon-f7="bars"></f7-button>
      </div>
    </f7-appbar>
    <f7-panel left>
      <f7-list>
        <f7-list-button title="Beranda"></f7-list-button>
        <f7-list-button title="BBLR Rule"></f7-list-button>
        <f7-list-button title="Article"></f7-list-button>
        <f7-list-button @click="logout()" title="Logout"></f7-list-button>
      </f7-list>
    </f7-panel>
    <f7-view main>
      <f7-page>
        <f7-block strong>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Phasellus sed sagittis dui. Fusce nulla massa, scelerisque vitae auctor in, luctus in ipsum. Sed eu lectus vel magna malesuada lacinia. Ut at vestibulum sem. In semper, arcu pulvinar volutpat fermentum, felis magna fringilla felis, nec volutpat nisi nunc quis ante. Fusce elementum egestas tortor ut porta. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Duis id commodo elit. Sed massa dui, laoreet a orci sed, egestas vehicula tellus. Nulla pulvinar ornare justo sed finibus. Aliquam hendrerit dui at nulla eleifend, quis feugiat enim aliquam. Nulla facilisi. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.</p>
        </f7-block>
      </f7-page>
    </f7-view>
  </f7-app>
</template>

<script>
  export default {
    middleware: 'auth',
    data(){
      return {
        tets:"boo"
      }
    },
    mounted(){
      const consola = require('consola')

      let isLogin  = localStorage.getItem("is_login");
      consola.success(isLogin)
      if (isLogin === null){
        this.$f7router.navigate("/");
      }
    },
    methods:{
      logout(){
        localStorage.clear()
        const self = this;
        const app = self.$f7;

        this.$f7router.navigate("/");
      }
    }
  }
</script>
