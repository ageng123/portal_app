<template>
  <div>
    <b-container>
      <b-card
        variant="primary"
        header-tag="header"
        footer-tag="footer"
        class="mb-3 navy-border width-65vh"
        header-class="navy navy-border text-white"
        body-class="pb-0 text-justify"
      >
        <template v-slot:header>
          <h3>
            Login Form
          </h3>
        </template>
        <b-form>
          <b-form-group
            id="input-group-1"
            label="Email address"
            label-for="input-1"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              id="input-1"
              type="email"
              required
              placeholder="Enter Your Email Address"
            />
          </b-form-group>
          <b-form-group id="input-group-2" label="Password" label-for="input-2">
            <b-input-group>
              <b-form-input
                id="input-2"
                :type="type"
                required
                placeholder="Enter Your Password"
              ></b-form-input>
              <b-input-group-append>
                <b-button variant="outline-dark" @click="showHideMethod()"><b-icon :icon="icon" /></b-button>
              </b-input-group-append>
            </b-input-group>
          </b-form-group>
          <b-form-group>
            <b-form-checkbox
            id="checkbox-1"
            v-model="status"
            name="checkbox-1"
            value="accepted"
            unchecked-value="not_accepted"
            >
              Remember Me!
            </b-form-checkbox>
          </b-form-group>
        </b-form>
        <b-btn block variant="success" class="mb-3" @click="setLogin()"><span><b-icon icon="unlock-fill"></b-icon></span> Login</b-btn>
      </b-card>
    </b-container>
  </div>
</template>
<script>
export default {
  name: 'LoginForm',
  data () {
    return {
      showPassword: false,
      icon: 'eye-slash-fill',
      type: 'password'
    }
  },
  watch: {
    showPassword () {
      this.icon = this.showPassword === false ? 'eye-slash-fill' : 'eye-fill'
      this.type = this.showPassword === false ? 'password' : 'text'
    }
  },
  methods: {
    showHideMethod () {
      this.showPassword === true ? (this.showPassword = false) : (this.showPassword = true)
    },
    setLogin () {
      sessionStorage.setItem('Authorization-Token', '09230182940812joidjqw9rq0wr80qw')
      window.location.reload()
    }
  }
}
</script>
<style>
  .width-65vh{
    width: 65vh
  }
</style>
