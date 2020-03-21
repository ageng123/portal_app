<template>
  <div>
    <b-navbar toggleable="lg" type="dark" class="navy" variant="info">
      <b-navbar-brand href="#">
        Nucleus Precise
      </b-navbar-brand>
      <b-navbar-toggle target="nav-collapse" />
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <div v-if="user_token == null" ></div>
          <template v-if="user_token != null">
            <b-nav-item to="notif" right>
              <b-icon icon="bell-fill">
              </b-icon>
              <b-badge href="" variant="danger">
                {{ badges }}
              </b-badge>
            </b-nav-item>
            <b-nav-item-dropdown right>
              <template v-slot:button-content>
                <em>User </em>
              </template>
              <b-dropdown-item href="#">
                Profile
              </b-dropdown-item>
              <b-dropdown-item @click="removeUserTOken()">
                Sign Out
              </b-dropdown-item>
            </b-nav-item-dropdown>
          </template>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>
<script>
export default {
  name: 'Navbar',
  components: {
  },
  data () {
    return {
      user: null,
      user_token: null,
      badges: 39
    }
  },
  mounted () {
    this.user_token = sessionStorage.getItem('Authorization-Token') ? sessionStorage.getItem('Authorization-Token') : null
  },
  methods: {
    setUserToken: () => {
      sessionStorage.setItem('Authorization-Token', '09230182940812joidjqw9rq0wr80qw')
      window.location.reload()
    },
    removeUserTOken: () => {
      sessionStorage.removeItem('Authorization-Token')
      window.location.reload()
    }
  }
}
</script>
<style>
.navy{
  background-color: navy !important;
}
.navy-border{
  border-color: navy !important;
}
</style>
