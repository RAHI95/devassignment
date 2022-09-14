<template>
  <div>
     <div id="">
      <div class="accordion" id="accordionExample">
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingOne">
      <button class="d-flex bg-white mx-auto">
        <a @click="leaveScreen = true" class="click-me">User</a>
        <a href="#" class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="false" aria-controls="collapseOne"></a>
      </button>
    </h2>
  </div>
  <div class="accordion-item">
    <h2 class="accordion-header" id="headingTwo">
      <button class="d-flex bg-white mx-auto">
        <a @click="toggleTheme">View</a>
        <a href="" class="accordion-button " type="button" data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="true" aria-controls="collapseTwo"></a>
      </button>
    </h2>
  </div>
  <div>
    <div id="collapseOne" class="accordion-collapse collapse " aria-labelledby="headingOne" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        <strong>User Content</strong>
         <p>It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the though the transition does limit overflow.</p> 
      </div>
    </div>
    <div id="collapseTwo" class="accordion-collapse collapse show" aria-labelledby="headingTwo" data-bs-parent="#accordionExample">
      <div class="accordion-body">
        <strong>View Content</strong> 
        <p>It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the though the transition does limit overflow.</p> 
      </div>
    </div>
  </div>
</div>
    </div>
    <transition name="leave-screen">
    <div v-if="leaveScreen" class="leave-screen" @click="leaveScreen = false"></div>
  </transition>
  </div>
</template>

<script>
export default {
  data(){
        return{
          leaveScreen: false
        }
    },
    methods:{
      toggleTheme(){
        // alert('clicked')
          this.isActive = !this.isActive;
      }
    }
};
</script>

<style>
  body {
  margin: 0;
}

.click-me {
  cursor: pointer;
  font-size: 30px;
}

.leave-screen {
  position: absolute;
  height: 100vh;
  width: 100vw;
  top: 0;
  background-color: rgb(0, 0, 0);
}
.leave-screen-enter-active,
.leave-screen-leave-active {
  background-color: rgba(0, 0, 0, 1);
  transform: translateX(0);
  transition: all 1s ease-in-out;
}

.leave-screen-leave-to,
.leave-screen-enter {
  background-color: rgba(0, 0, 0, 0);
  transform: translateX(-100%);
}

</style>