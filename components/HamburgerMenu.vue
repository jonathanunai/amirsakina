<template>
  <div id="webapp_cover" @click.prevent="toggleMenu">
    <div id="menu_button">
      <input id="menu_checkbox" type="checkbox" :checked="menuIsOpen" />
      <label id="menu_label" for="menu_checkbox">
        <div id="menu_text_bar"></div>
      </label>
    </div>
    <transition name="slide">
      <div v-if="menuIsOpen" class="menu">
        <ul>
          <li @click="$emit('moveTo', 0)">Home</li>
          <li @click="$emit('moveTo', 1)">Presentation</li>
          <li @click="$emit('moveTo', 2)">Quote</li>
          <li @click="$emit('moveTo', 3)">Gallery</li>
          <li @click="$emit('moveTo', 4)">Events</li>
        </ul>
      </div>
    </transition>
  </div>
</template>
<script>
export default {
  data() {
    return {
      menuIsOpen: false,
    }
  },
  methods: {
    toggleMenu() {
      this.menuIsOpen = !this.menuIsOpen
    },
  },
}
</script>
<style scoped>
* {
  -webkit-tap-highlight-color: transparent;
}

*:focus {
  outline: none;
}

#webapp_cover {
  position: fixed;
  top: 0.73rem;
  left: 0.73rem;
  width: 39px;
  margin: 0;
  padding: 0.5rem;
  z-index: 3;
}

#menu_button {
  width: 39px;
  overflow: hidden;
  z-index: 3;
}

#menu_checkbox {
  display: none;
}

#menu_label {
  position: relative;
  display: block;
  height: 29px;
  cursor: pointer;
}

#menu_label:before,
#menu_label:after,
#menu_text_bar {
  position: absolute;
  left: 0;
  width: 100%;
  height: 5px;
  background-color: #fff;
  z-index: 5;
}

#menu_label:before,
#menu_label:after {
  content: '';
  transition: 0.4s cubic-bezier(0.68, -0.55, 0.27, 1.55) left;
}

#menu_label:before {
  top: 0;
}

#menu_label:after {
  top: 12px;
}

#menu_text_bar {
  top: 24px;
}

#menu_text_bar:before {
  content: 'MENU';
  position: absolute;
  top: 5px;
  right: 0;
  left: 0;
  color: #fff;
  font-size: 12px;
  font-weight: bold;
  font-family: 'Montserrat', Arial, Helvetica, sans-serif;
  text-align: center;
  z-index: 5;
}

#menu_checkbox:checked + #menu_label:before {
  left: -39px;
}

#menu_checkbox:checked + #menu_label:after {
  left: 39px;
}

#menu_checkbox:checked + #menu_label #menu_text_bar:before {
  animation: moveUpThenDown 0.8s ease 0.2s forwards,
    shakeWhileMovingUp 0.8s ease 0.2s forwards,
    shakeWhileMovingDown 0.2s ease 0.8s forwards;
}
.menu {
  position: fixed;
  top: 0;
  left: 0;
  background: #5738bf;
  color: #fff;
  padding: 5rem 1rem;
  margin: 0;
  z-index: 0;
  width: 80%;
  max-width: 400px;
  border-radius: 0 0 5rem 0;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.72);
  font-size: 1.4rem;
}
li {
  cursor: pointer;
  margin-bottom: 4px;
}

@keyframes moveUpThenDown {
  0% {
    top: 0;
  }
  50% {
    top: -27px;
  }
  100% {
    top: -14px;
  }
}

@keyframes shakeWhileMovingUp {
  0% {
    transform: rotateZ(0);
  }
  25% {
    transform: rotateZ(-10deg);
  }
  50% {
    transform: rotateZ(0deg);
  }
  75% {
    transform: rotateZ(10deg);
  }
  100% {
    transform: rotateZ(0);
  }
}

@keyframes shakeWhileMovingDown {
  0% {
    transform: rotateZ(0);
  }
  80% {
    transform: rotateZ(3deg);
  }
  90% {
    transform: rotateZ(-3deg);
  }
  100% {
    transform: rotateZ(0);
  }
}
.show-enter-active,
.show-leave-enter {
  transform: translateX(0);
  transition: all 0.3s linear;
}
.show-enter,
.show-leave-to {
  transform: translateX(-100%);
}

.slide-leave-active,
.slide-enter-active {
  transition: 0.6s;
}
.slide-enter {
  transform: translate(-100%, 0);
}
.slide-leave-to {
  transform: translate(-100%, 0);
}

.slideback-leave-active,
.slideback-enter-active {
  transition: 1s;
}
.slideback-enter {
  transform: translate(-100%, 0);
}
.slideback-leave-to {
  transform: translate(-100%, 0);
}
</style>
