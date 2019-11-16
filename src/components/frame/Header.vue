<template>
  <div fixed="top">
    <b-card  no-body>
      <b-card-header  header-tag="nav" class="bg-success">
        <b-nav  card-header tabs>
         <b-nav @click="redirect('/Login')" v-if="auth.user ===null" id="login">Sign In</b-nav>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          <b-nav @click="redirect('/Register')" v-if="auth.user ===null" id="signup">Sign Up</b-nav>
        </b-nav>
      </b-card-header>

     
    </b-card>
  </div>
</template>
<style scoped > 
 /* @import "assets/style.scss"; */
#login{
  color:white;
  font-size: 20px;
  position: absolute;
  right:50px;
}
#signup{
  color:white;
  font-size: 20px;
  position: absolute;
  right:130px;
 
}


</style>
<script>
import AUTH from 'services/auth'
import ROUTER from "router";
export default {
  data(){
    return {
      auth: AUTH
    }
  },
  methods: {
    redirect(router) {
      ROUTER.push(router);
    }
  }
};
</script>
