<template>
  <div>
    <div id="">
      
      <div class="accordion" id="accordionExample">
        <transition name="button" mode="out-in">
          <div class="accordion-item"  v-if="!showOnButton">
            <h2 class="accordion-header" id="headingOne">
              <button class="d-flex bg-white mx-auto">
                <a @click.prevent="onShowButton()">User</a>
                <a
                  href="#"
                  class="accordion-button collapsed"
                  type="button"
                  data-bs-toggle="collapse"
                  data-bs-target="#collapseOne"
                  aria-expanded="false"
                  aria-controls="collapseOne"
                ></a>
              </button>
            </h2>
          </div>
          <div v-else class="accordion-item">
            <h2 class="accordion-header" id="headingTwo">
              <button class="d-flex bg-white mx-auto">
                <a 
                @click.prevent="onShowButton()" >View</a>
                <a
                  href=""
                  class="accordion-button"
                  type="button"
                  data-bs-toggle="collapse"
                  data-bs-target="#collapseTwo"
                  aria-expanded="true"
                  aria-controls="collapseTwo"
                ></a>
              </button>
            </h2>
          </div>
        </transition>
        <div>
          <div
            id="collapseOne"
            class="accordion-collapse collapse"
            aria-labelledby="headingOne"
            data-bs-parent="#accordionExample"
          >
            <div class="accordion-body">
              <strong>User Content</strong>
              <p>
                It is shown by default, until the collapse plugin adds the
                appropriate classes that we use to style each element. These
                classes control the overall appearance, as well as the showing
                and hiding via CSS transitions. You can modify any of this with
                custom CSS or overriding our default variables. It's also worth
                noting that just about any HTML can go within the though the
                transition does limit overflow.
              </p>
            </div>
          </div>
          <div
            id="collapseTwo"
            class="accordion-collapse collapse show"
            aria-labelledby="headingTwo"
            data-bs-parent="#accordionExample"
          >
            <div class="accordion-body">
              <strong>View Content</strong>
              <p>
                It is shown by default, until the collapse plugin adds the
                appropriate classes that we use to style each element. These
                classes control the overall appearance, as well as the showing
                and hiding via CSS transitions. You can modify any of this with
                custom CSS or overriding our default variables. It's also worth
                noting that just about any HTML can go within the though the
                transition does limit overflow.
              </p>
            </div>
          </div>
        </div>

      </div>
   
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showOnButton: false,

    };
  },
  computed: {
    transition() {
      return this.isSlide;
    },
  },
  methods: {
    onShowButton() {
            this.showOnButton = !this.showOnButton;
        },
    shouldSlide() {
      this.isSlide = true;
      this.show = false;
      setTimeout(() => {
        this.show = true;
      }, 0);
    },
    shouldFade() {
      this.isSlide = false;
      this.show = false;
      setTimeout(() => {
        this.show = true;
      }, 0);
    },
  },
};
</script>

<style>
 .button-enter-from,
button-leave-to {
    /* opacity: 0; */
    transform: translateY(30px);
}
.button-enter-to,
.button-leave-from {
    /* opacity: 1; */
    transform: translateY(0px);
}
.button-enter-active,
.button-leave-active {
    transition: all 1s;
}
</style>