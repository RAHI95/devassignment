<template>
  <div>
    <div id="">
      <div class="accordion" id="accordionExample">
        <div class="accordion-item">
          <h2 class="accordion-header" id="headingOne">
            <transition-group tag="ul">
              <li v-for="item in list" :key="item.name">
                <button class="d-flex bg-white mx-auto">
                  <a @click="reorder">{{ item.name }}</a>
                  <a
                    href="#"
                    class="accordion-button collapsed"
                    type="button"
                    data-bs-toggle="collapse"
                    :data-bs-target="`#${item.id}`"
                    aria-expanded="false"
                    :aria-controls="`${item.id}`"
                  ></a>
                </button>
              </li>
            </transition-group>
          </h2>
        </div>
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
                as well as the showing
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
      list: [
        {
          name: "User",
          id: "collapseOne",
        },
        {
          name: "view",
          id: "collapseTwo",
        },
      ],
    };
  },

  methods: {
    onShowButton() {
      this.showOnButton = !this.showOnButton;
    },
    reorder() {
      this.list.unshift(this.list[this.list.length - 1]);
      this.list.splice(this.list.length - 1, 1);
    },
  },
};
</script>
<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
button {
  display: block;
}

li {
  transition: 0.5s;
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.5s;
}

.v-leave-active {
  position: absolute;
}

.v-enter,
.v-leave-to {
  opacity: 0;
}
</style>