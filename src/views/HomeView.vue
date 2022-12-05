<template lang="">
  <div id="body" class="row">
    <div class="background col s12 no-padding">
      <div class="overlay col s12">
        <img class="left" :src="img" />
        <div class="_container col s12 m8 l6 push-l2 xl4 push-xl3 no-padding">
          <h2 class="white-text">Our New Website Will Launch Soon.</h2>
          <P class="white-text"
            >Please be patient. We are working on something awesome. You can
            still contact us if you are interested in Solar PV (for
            Electricity). Just enter your email address and number below and we
            will contact you.</P
          >

          <div class="col s10 no-padding">
            <div
              class="input-field col s12 no-padding no-margin browser-default"
            >
              <input
                class="white"
                type="email"
                name="email"
                id="email"
                v-model="submit.email"
                placeholder="E-mail Address"
              />
            </div>

            <div
              class="input-field col s12 no-padding no-margin browser-default"
            >
              <input
                class="white"
                type="tel"
                name="Contact Number"
                id="contact"
                v-model="submit.contact"
                placeholder="Contact Number"
              />
            </div>

            <button class="btn-flat light-green rounded regular-case col s7">
              Submit
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import img from "@/assets/Noah-Logo-Final Lockup-Colour on white.png";
export default {
  name: "HomeView",

  data() {
    return {
      img,

      submit: {
        email: "",
        contact: "",
      },
    };
  },
};
</script>

<style lang="scss">
.row {
  margin: 0;
}

#body {
  height: 100vh;

  .overlay {
    height: 100%;
    padding: 50px;
    @media screen and (max-width: 992px) {
      padding: 30px;
    }
    background-color: rgba(0, 0, 0, 0.4);
  }
}

.background {
  background-repeat: no-repeat;
    background-size: cover;
    background-position: 50% center;
    background-image: url("https://images.unsplash.com/photo-1470137430626-983a37b8ea46?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80");
  height: 100%;
}

h2 {
  font-weight: 800;
  text-transform: uppercase;
}

input {
  border: 1px solid white !important;
  border-radius: 5px !important;
  box-shadow: none !important;
  text-indent: 10px;
  margin-bottom: 20px !important;
  height: 40px !important;
}

.no-padding {
  padding: 0 !important;
}

.no-margin {
  margin: 0 !important;
}

.regular-case {
  text-transform: capitalize;
  font-weight: 500;
}

.rounded {
  border-radius: 50px;
}

._container {
  position: relative;
  top: 45%;
  transform: translateY(-50%);
}

img {
  height: 46px;
}

input:-webkit-autofill {
  transition: background-color 5000s ease-in-out 0s !important;
}
</style>
