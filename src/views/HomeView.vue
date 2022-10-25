<template>
  <div
    class="row purple no-margin hold"
    style="--primary: #880e4f; --secondary: #00000"
  >
    <div
      class="col l8 m12 s12 box_1 animate__animated animate__fadeIn no-padding"
      :class="viewLeft === 'explore' ? ' ' : 'white animate__slideInLeft'"
    >
      <div
        class="viewLeft animate__animated animate_fadeIn"
        v-if="viewLeft === 'explore'"
        :class="viewLeft === 'bookTour' ? 'animate__fadeOut' : ' '"
      >
      <div class="col s12">
        <button class="btn-flat _contact right col s6 hide-on-large-only" @click="_nextView">
          <span class="right amber-text text-lighten-5">Contact</span>
        </button>
      </div>
        
        <h3 class="no-top-margin amber-text text-lighten-5">
          Dauphin Bio-Cultural Tour
        </h3>

        <button class="btn-flat bttn" @click="_nextView">
          <span class="left amber-text text-lighten-5">explore</span>
          <i class="material-icons right amber-text text-lighten-5">east</i>
        </button>
      </div>

      <div
        class="info animate__animated animate__slideInLeft"
        v-if="viewLeft === 'bookTour' || viewLeft === 'bookMobile'"
      >
        <button class="btn-flat right bttn_close no-padding" @click="_nextView">
          <i class="material-icons purple-text">close</i>
        </button>

        <button @click="_nextView" class="btn-flat bttn_bt purple-text hide-on-med-and-down">
          Book Tour
        </button>

        <button @click="bookTourMobile" class="btn-flat bttn_bt purple-text" v-if="viewLeft === 'bookTour'">
          Book Tour
        </button>

        <button class="btn-flat left bttn_close no-padding" @click="bookTourMobile" v-if="viewLeft === 'bookMobile'">
          <i class="material-icons purple-text">west</i>
        </button>

        <br />
        <br />
        <br />

        <h3 class="no-top-margin purple-text heading">Dauphin Bio-Cultural Tour</h3>

        <div class="book_mobile right col s12 no-padding" v-if="viewLeft === 'bookMobile'">
          <form class="animate__animated animate__fadeIn">
            <h1 class="purple-text no-margin">Book Tour</h1> 
            <input
              v-model="submit.name"
              type="text"
              class="input"
              id="name"
              name="Name"
              placeholder="Name"
            />
            <input
              v-model="submit.numberOfPersons"
              type="text"
              class="input"
              id="noPersons"
              name="Number of Persons"
              placeholder="Number of Persons"
            />
            <input
              v-model="submit.date"
              type="text"
              class="input"
              id="date"
              name="Date"
              placeholder="Date"
            />
            <input
              v-model="submit.email"
              type="text"
              class="input"
              id="email"
              name="Email"
              placeholder="E-mail"
            />
            <input
              v-model="submit.contactNumber"
              type="text"
              class="input"
              id="contactNumber"
              name="Contact Number"
              placeholder="Contact Number"
            />
          </form>
          <button
            class="btn-flat purple-text bttn bttn-form col s12"
            type="submit"
            name="action"
          >
            Submit
          </button>
        </div>

        <p v-if="viewLeft === 'bookTour'">
          Dauphin is recognized as one of Saint Lucia's premiere archaeological
          heritage sites, with its iconic Amerindian petrogliph, stone bowls and
          mysterious unique cascade looking, monolith, elongated pillar-like
          rocks, lying in close proximity. There are remnants of the old
          pre-revolutionary era church, a prison and a kiln construted in
          masonry attached to the rock cliff.
        </p>

        <p v-if="viewLeft === 'bookTour'">
          The area had been neglected, underutilized, vandalized and is now
          vulnerable to becoming an endangered heritage site. Generally, Dauphin
          remains understudied geologically and archaeologically. It has not
          been adequately reseacrhed and developed into the valuable hritage
          site that it has th epotential to be so that it can benefit the
          community both socially and economically.
        </p>

        <p v-if="viewLeft === 'bookTour'">The tour takes you on a journey thorugh the community.</p>
      </div>
    </div>

    <div
      class="col l4 box_2 animate__animated"
      :class="viewRight === 'rightView' ? ' ' : 'white animate__slideInRight'"
    >
      <div
        v-if="viewRight === 'rightView'"
        class="viewRight animate__animated animate__fadeIn"
        :class="viewLeft === 'bookTour' ? 'animate__fadeOut' : ' '"
      >
        <button class="btn-flat _contact right col s7" @click="_NextView">
          <span class="right amber-text text-lighten-5">Contact</span>
        </button>

        <div class="bookTour right col s12 no-padding">
          <form>
            <h1 class="purple-text no-margin">Book Tour</h1>
            <input
              v-model="submit.name"
              type="text"
              class="input"
              id="name"
              name="Name"
              placeholder="Name"
            />
            <input
              v-model="submit.numberOfPersons"
              type="text"
              class="input"
              id="noPersons"
              name="Number of Persons"
              placeholder="Number of Persons"
            />
            <input
              v-model="submit.date"
              type="text"
              class="input"
              id="date"
              name="Date"
              placeholder="Date"
            />
            <input
              v-model="submit.email"
              type="text"
              class="input"
              id="email"
              name="Email"
              placeholder="E-mail"
            />
            <input
              v-model="submit.contactNumber"
              type="text"
              class="input"
              id="contactNumber"
              name="Contact Number"
              placeholder="Contact Number"
            />
          </form>
          <button
            class="btn-flat amber-text text-lighten-5 right bttn col l12"
            type="submit"
            name="action"
          >
            Submit
          </button>
        </div>
      </div>

      <div v-if="viewRight === 'contact'" class="info">
        <div class="btn-flat contact right col s6">
          <span class="right purple-text">Contact</span>
        </div>

        <button class="btn-flat left bttn_close" @click="_NextView">
          <i class="material-icons purple-text">close</i>
        </button>

        <div class="space col s12"></div>

        <div class="_info">
          <h3 class="no-top-margin purple-text">Laurent Jean-Pierre</h3>
          <p class="purple-text">Telephone</p>
          <h4 class="no-top-margin purple-text">+1-758-384-6434</h4>
          <p class="purple-text">Email</p>
          <h4 class="no-top-margin purple-text">
            laurentjean.pierre@gmail.com
          </h4>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeView",

  data() {
    return {
      viewLeft: "explore",
      viewRight: "rightView",

      submit: {
        name: "",
        numberOfPersons: "",
        date: "",
        email: "",
        contactNumber: "",
      },
    };
  },

  methods: {
    // Toggles the left side content and background when you click (explore) button
    _nextView() {
      if (this.viewLeft === "explore") {
        this.viewLeft = "bookTour";
        this.viewRight = "rightView";
      } else {
        this.viewLeft = "explore";
      }
    },

    bookTourMobile() {
      if (this.viewLeft === "bookTour") {
        this.viewLeft = "bookMobile"
      } else {
        this.viewLeft = "bookTour"
      }
    },

    // Toggles the right side content and background when you click (contact) button
    _NextView() {
      if (this.viewRight === "rightView") {
        this.viewRight = "contact";
        this.viewLeft = "explore";
      } else {
        this.viewRight = "rightView";
      }
    },
  },
};
</script>

<style lang="scss">
.row {
  height: 100vh;
  // background-image: url(../assets/omar-eagle-clarke-bG_xVUDGiQw-unsplash.jpg);
  background-image: url(../assets/Dauphin_St._Lucia.jpg);
  // background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
  box-shadow: inset 0 0 0 1000px rgba(192, 35, 171, 0.281);
  // box-shadow: inset 0 0 0 1000px rgba(0, 0, 0, 0.5);
  // padding: 100px;
  // @media screen and (max-width: 992px) {
  //   overflow: hidden;
  // }

  overflow: hidden;
}

.box_1,
.box_2 {
  height: 100vh;

  .bttn_close i {
    font-size: 30px;
  }

  .bttn {
    border: solid 1px #fff8e1 !important;
    width: 150px;
    height: 40px !important;
  }
}

.box_1 {
  .viewLeft {
    padding: 100px 0 100px 100px;
    @media screen and (max-width:992px) {
        padding: 24px;
      }

    height: 100%;

    h3 {
      font-weight: 600;
      margin-bottom: 24px;
      @media screen and (max-width: 600px) {
        font-size: 26px;
}
    }

    .bttn, h3 {
      position: relative;
      top: 60%;
    }
  }

  .heading {
        @media screen and (max-width:992px) {
          font-size: 24px;
        }
      }

  .bttn_bt {
    border: solid 1px var(--primary);
    width: 150px;
    &:focus {
      background-color: var(--primary);
      color: white;
    }
  }

  .bttn-form {
      border-color: var(--secondary) !important;
    }
}

.box_2 {
  @media screen and (max-width:992px) {
    display: none;
  }
  .viewRight {
    padding: 100px 100px 100px 0;
    height: 100%;
    display: inline-block;

    @media screen and (max-width:992px) {
        padding: 24px;
      }
  }

  ._contact .contact {
    font-size: 18px;
    height: 40px !important;
    padding-right: 5px !important;
  }

  .contact {
    border-bottom: solid 1px var(--primary) !important;
  }
}

.bookTour, .book_mobile {
  form {
    height: auto;
    padding: 24px !important;
    background-color: #cbbb8684;
    margin-bottom: 10px;
  }

  h1 {
    font-size: 24px;
    font-weight: 600;
    margin-bottom: 10px !important;
  }
}

.bookTour {
  position: relative;
  top: 15%;
}

.book_mobile {
  input {
    color: black;
    &::placeholder {
      color: var(--primary);
    }
  }
}

input {
  font-weight: 500;
  color: white;

  border-color: var(--primary) !important;
  &:focus {
    border-color: white !important;
  }

  box-shadow: none !important;
  &::placeholder {
    color: white;
  }
  &:-webkit-autofill {
    transition: background-color 5000s ease-in-out 0s !important;
    -webkit-text-fill-color: white;
  }
}

.info {
  padding: 50px;
  height: 100%;

  h3 {
    font-weight: 700;
    margin-bottom: 25px;
  }
}

._info {
  text-align: right;
  position: relative;
  top: 30%;

  p {
    font-weight: 700;
  }
}

._contact {
    border-bottom: solid 1px #fff8e1 !important;
  }

  .bttn-form {
      border-color: var(--secondary) !important;
    }
</style>
