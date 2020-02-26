<template>
  <div id="drop-down-menu">
    <div>
      <div 
        class="sandwich" 
        @click="show_menu = !show_menu">
        <a class="noselect">=</a>
        <transition name="fade">
          <div 
            class="drop-down"
            v-show='show_menu'>
            <router-link 
              class="menu-item" 
              to="/">
                <a class="menu-text">  
                  Home
                </a>
            </router-link>
            <br><br>
            <router-link 
              class="menu-item" 
              to="/about">
                <a class="menu-text">  
                  About
                </a>
            </router-link>
            <br><br>
            <div v-show="!$auth.isAuthenticated" class="menu-item">
                <a 
                  class="menu-text"
                  @click="login">  
                  Login
                </a>
            </div>
            <div v-show="$auth.isAuthenticated" class="menu-item">
                <a 
                  class="menu-text"
                  @click="logout">  
                  Logout
                </a>
            </div>
          </div>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NavBar',
  data() {
    return {
      show_menu: false
    }
  },
  computed: {

  },
  methods: {
    // Log the user in
    login() {
      this.$auth.loginWithRedirect();
    },
    // Log the user out
    logout() {
      this.$auth.logout({
        returnTo: window.location.origin
      });
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.menu-item {
  text-decoration: none;
  width: 100%;
}

.menu-text { 
  color: rgb(2, 12, 20);
  padding-left: 10px;
}

.drop-down{
  width: 100px;
  background-color: rgb(137, 212, 235);
  text-align: left;
  line-height: 1em;
  margin-top: 3.5px;
  margin-left: -1px;
  padding: 5px;
  padding-bottom: 10px;
  padding-top: 10px;
}

.sandwich {
  color: rgb(2, 12, 20);
  border-color: rgb(137, 212, 235);
  color: rgb(137, 212, 235);
  background-color: transparent;
  border-style: solid;
  border-width: 1.3px;
  width: 25px;
  height: 25px;
  text-align: center;
  cursor: pointer;
}

.noselect {
  -webkit-touch-callout: none; /* iOS Safari */
  -webkit-user-select: none; /* Safari */
  -khtml-user-select: none; /* Konqueror HTML */
  -moz-user-select: none; /* Old versions of Firefox */
  -ms-user-select: none; /* Internet Explorer/Edge */
  user-select: none; /* Non-prefixed version, currently */
}

.fade-enter-active, .fade-leave-active {
  transition: 0.05s;
  transform: scale(1);
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  transform: scale(0);
  opacity: 0;
}

</style>
