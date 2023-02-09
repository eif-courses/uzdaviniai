<template>
  <div id="app">
aweaweaw
erawr

se

    <div class="surface-overlay py-3 px-6 shadow-2 flex align-items-center justify-content-between relative lg:static">
      <img src="/images/blocks/logos/hyper.svg" alt="Image" height="50" class="mr-0 lg:mr-5">
      <a
          v-ripple
          class="cursor-pointer block text-700 mt-1 p-ripple"
          @click="isOpen = !isOpen"
      >
        <i class="pi pi-bars text-4xl" />
      </a>
      <div :class="{ hidden: isOpen }" class="close_open_menu align-items-center flex-grow-1 justify-content-between lg:flex absolute lg:static w-full surface-overlay left-0 top-100 px-6 lg:px-0 z-4 shadow-2 lg:shadow-none">
        <ul class="list-none p-0 m-0 flex lg:align-items-center text-900 select-none flex-column lg:flex-row cursor-pointer">

          <li class="relative">
            <a
                v-ripple to="/main"
                class="navigation-style flex px-0 lg:px-5 py-3 align-items-center hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple"
            >
              <span>Guides</span>
              <i class="pi pi-chevron-down ml-auto lg:ml-3" />
            </a>
            <div class="border-round shadow-0 lg:shadow-2 lg:absolute surface-overlay hidden my-2 lg:my-0 w-full lg:w-30rem">
              <div class="grid">
                <div class="col-12 lg:col-6">
                  <a v-ripple class="flex p-3 align-items-center hover:surface-50 transition-colors transition-duration-150 border-round p-ripple">
                    <div class="p-2 border-round bg-blue-600 text-0 mr-3">
                      <i class="pi pi-list text-2xl" />
                    </div>
                    <div>
                      <span>Features</span>
                      <div class="text-600 text-sm mt-1">Subtext of item</div>
                    </div>
                  </a>
                </div>
                <div class="col-12 lg:col-6">
                  <a v-ripple class="flex p-3 align-items-center hover:surface-50 transition-colors transition-duration-150 border-round p-ripple">
                    <div class="p-2 border-round bg-blue-600 text-0 mr-3">
                      <i class="pi pi-shield text-2xl" />
                    </div>
                    <div>
                      <span>Solutions</span>
                      <div class="text-600 text-sm mt-1">Subtext of item</div>
                    </div>
                  </a>
                </div>
                <div class="col-12 lg:col-6">
                  <a v-ripple class="flex p-3 align-items-center hover:surface-50 transition-colors transition-duration-150 border-round p-ripple">
                    <div class="p-2 border-round bg-blue-600 text-0 mr-3">
                      <i class="pi pi-users text-2xl" />
                    </div>
                    <div>
                      <span>Customers</span>
                      <div class="text-600 text-sm mt-1">Subtext of item</div>
                    </div>
                  </a>
                </div>
                <div class="col-12 lg:col-6">
                  <a v-ripple class="flex p-3 align-items-center hover:surface-50 transition-colors transition-duration-150 border-round p-ripple">
                    <div class="p-2 border-round bg-blue-600 text-0 mr-3">
                      <i class="pi pi-question-circle text-2xl" />
                    </div>
                    <div>

                      <span>Faq</span>
                      <div class="text-600 text-sm mt-1">Subtext of item</div>
                    </div>
                  </a>
                </div>
                <div class="col-12 lg:col-6">
                  <a v-ripple class="flex p-3 align-items-center hover:surface-50 transition-colors transition-duration-150 border-round p-ripple">
                    <div class="p-2 border-round bg-blue-600 text-0 mr-3">
                      <i class="pi pi-file text-2xl" />
                    </div>
                    <div>
                      <span>Case Studies</span>
                      <div class="text-600 text-sm mt-1">Subtext of item</div>
                    </div>
                  </a>
                </div>
                <div class="col-12 lg:col-6">
                  <a v-ripple class="flex p-3 align-items-center hover:surface-50 transition-colors transition-duration-150 border-round p-ripple">
                    <div class="p-2 border-round bg-blue-600 text-0 mr-3">
                      <i class="pi pi-search text-2xl" />
                    </div>
                    <div>
                      <span>Library</span>
                      <div class="text-600 text-sm mt-1">Subtext of item</div>
                    </div>
                  </a>
                </div>
              </div>
            </div>
          </li>


          <div>
            <li>
              <router-link to="/home" class="navigation-style flex px-0 lg:px-5 py-3 hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple" @click="isOpen = !isOpen">
                <span>Home</span>
              </router-link>
            </li>
            <li v-if="showAdminBoard">
              <router-link to="/admin" class="navigation-style flex px-0 lg:px-5 py-3 hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple" @click="isOpen = !isOpen">Admin Board</router-link>
            </li>
            <li v-if="showModeratorBoard">
              <router-link to="/mod" class="navigation-style flex px-0 lg:px-5 py-3 hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple" @click="isOpen = !isOpen">Moderator Board</router-link>
            </li>
            <li>
              <router-link v-if="currentUser" to="/user" class="navigation-style flex px-0 lg:px-5 py-3 hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple" @click="isOpen = !isOpen">User</router-link>
            </li>
          </div>

          <div v-if="!currentUser">
            <li>
              <router-link to="/register" class="navigation-style flex px-0 lg:px-5 py-3 hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple" @click="isOpen = !isOpen">
                <span>Sign Up</span>
              </router-link>
            </li>
            <li>
              <router-link to="/login" class="navigation-style flex px-0 lg:px-5 py-3 hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple" @click="isOpen = !isOpen">
                <span>Login</span>
              </router-link>
            </li>
          </div>

          <div v-if="currentUser">
            <li>
              <router-link to="/profile" class="navigation-style flex px-0 lg:px-5 py-3 hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple" @click="isOpen = !isOpen">
                <span>{{ currentUser.username }}</span>
              </router-link>
            </li>
            <li>
              <a class="navigation-style flex px-0 lg:px-5 py-3 hover:text-blue-600 font-medium transition-colors transition-duration-150 p-ripple" @click="isOpen = !isOpen" href @click.prevent="logOut">
                <span>LogOut</span>
              </a>
            </li>
          </div>
        </ul>
        <div class="flex justify-content-between lg:block border-top-1 lg:border-top-none surface-border py-3 lg:py-0 mt-3 lg:mt-0">
          <router-link to="/login" custom v-slot="{ navigate }">
          <Button label="Login" @click="navigate" role="link" class="p-button-text font-bold" />
          </router-link>
          <router-link to="/register" custom v-slot="{ navigate }">
          <Button label="Register" @click="navigate" class="ml-3 font-bold" />
          </router-link>
        </div>
      </div>
    </div>






    <nav class="navbar navbar-expand navbar-dark bg-dark">

      <a href class="navbar-brand" @click.prevent>bezKoder</a>
      <div class="navbar-nav mr-auto">
        <li class="nav-item">
          <router-link to="/home" class="nav-link">
            <font-awesome-icon icon="home" />Home
          </router-link>
        </li>
        <li v-if="showAdminBoard" class="nav-item">
          <router-link to="/admin" class="nav-link">Admin Board</router-link>
        </li>
        <li v-if="showModeratorBoard" class="nav-item">
          <router-link to="/mod" class="nav-link">Moderator Board</router-link>
        </li>
        <li class="nav-item">
          <router-link v-if="currentUser" to="/user" class="nav-link">User</router-link>
        </li>
      </div>

      <div v-if="!currentUser" class="navbar-nav ml-auto">
        <li class="nav-item">
          <router-link to="/register" class="nav-link">
            <font-awesome-icon icon="user-plus" />Sign Up
          </router-link>
        </li>
        <li class="nav-item">
          <router-link to="/login" class="nav-link">
            <font-awesome-icon icon="sign-in-alt" />Login
          </router-link>
        </li>
      </div>

      <div v-if="currentUser" class="navbar-nav ml-auto">
        <li class="nav-item">
          <router-link to="/profile" class="nav-link">
            <font-awesome-icon icon="user" />
            {{ currentUser.username }}
          </router-link>
        </li>
        <li class="nav-item">
          <a class="nav-link" href @click.prevent="logOut">
            <font-awesome-icon icon="sign-out-alt" />LogOut
          </a>
        </li>
      </div>
    </nav>

    <div class="container">
      <router-view />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {isOpen: true}
  },

  computed: {
    currentUser() {
      return this.$store.state.auth.user;
    },
    showAdminBoard() {
      if (this.currentUser && this.currentUser.roles) {
        return this.currentUser.roles.includes('ROLE_ADMIN');
      }

      return false;
    },
    showModeratorBoard() {
      if (this.currentUser && this.currentUser.roles) {
        return this.currentUser.roles.includes('ROLE_MODERATOR');
      }

      return false;
    }
  },
  methods: {
    logOut() {
      this.$store.dispatch('auth/logout');
      this.$router.push('/login');
    }
  }
};
</script>
