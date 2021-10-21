<template>
  <div class="mdWrapper">
      <img :src="require('../assets/images/logo.png')" alt="Keyclock OIDC"/>
      <h3>mIdentity Box Demo</h3>
      <h4>Vue JS - Implicit flow authentication</h4>
      <p>Welcome <strong>{{username}}</strong></p>
      <button class="btn-normal" v-on:click="userLogout">Logout</button>
  </div>
</template>

<script>
  import Keycloak from 'keycloak-js';
  import { CookieName, Config } from '../model/Config';
  import { parseToken, GetCookieValue, DeleteCookieValue } from '../model/Functions';
  //keycloak init options
  let keycloak = Keycloak(Config);
  export default {
    name: 'AuthorisedPage',
    created: function(){
      keycloak.init({ flow: 'implicit', checkLoginIframe: false }).then((authenticated) => {
        try{
          if(authenticated)
            console.log("Authenticated");
        }
        catch(error){
          console.log("Authenticated failed due to \n" + error);
        }
      })
      if(!GetCookieValue(CookieName)){
        this.$router.push({name: 'Home'});
      }
    },
    data: function(){
      return {
        username: parseToken(GetCookieValue(CookieName)).preferred_username
      }
    },
    methods: {
      userLogout: function (){
        keycloak.logout({redirectUri: window.location.origin})
        DeleteCookieValue(CookieName);
      }
    }
  }
</script>
