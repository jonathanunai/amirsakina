<template>
  <div class="fullpage-container">
    <HamburgerMenu @moveTo="moveTo"/>
    <div ref="webpages" v-fullpage="opts" class="fullpage-wp">
      <div class="page-1 page">
        <div class="part part-1">
          <div class="hearts">
            <div class="heart"></div>
            <div class="heart"></div>
            <div class="heart"></div>
            <div class="heart"></div>
          </div>

          <div style="z-index: 11">
            <h1
              v-animate="{ value: 'bounceInLeft', delay: 300 }"
              class="part-3"
            >
              Amir
            </h1>
            <h2
              v-animate="{ value: 'bounceInRight', delay: 900 }"
              class="part-3"
            >
              &
            </h2>
            <h1 v-animate="{ value: 'zoomIn', delay: 1500 }" class="part-3">
              Sakina
            </h1>
          </div>
        </div>
        <div class="down" @click="moveNext">
          <img
            src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADIAAAAyCAYAAAAeP4ixAAAABmJLR0QA/wD/AP+gvaeTAAABEklEQVRoge2WOQ7CQAxF/yWI4P43gQoEDRQcJxQwEkJYePdI+NXx8jST5ANN0zRN48sewBnAUr3IFxYAFwAHzsMnACuAG+aSWfDcaQVw5BRsAFxfBXcAu7DV+HzutNUWVsqoJagGFTJmCapRpoybBNUwQ8ZdgmocKRMmQQ2IkAmXoAZ5yqRJUAM9ZNIlqMEWmTIJagGNTKiEJDS+5x9pNtPUhoZG7UKWmrDQKKnRXKfU0MipSZWQLCapKZHgLCapKZUYeLzMGR8DFtaTKT2JXwMkMtNIDLTXrPQ6UXRoZPbq0GjBIjONxMDjp1kuMYgOjalEhcYSvENjKV6hcQqsoXEqtKFxSqShcWq4obFpmuaPeABpoeiFZo2bFwAAAABJRU5ErkJggg=="
          />
        </div>
      </div>
      <div class="page-2 page">
        <div class="part part-2">
          <p class="yellow">بِسْمِ ٱللَّٰهِ ٱلرَّحْمَٰنِ ٱلرَّحِيم</p>
          <p>
            By the Grace of Allah, Vasila-e-Panjatan Pak (A.S), Aeemat Tahereen
            (A.S), Duat Mutlaqeen (A.Q) & Dua Mubarak of Dai-uz-Zaman Aaliqadr
            Syedna Mufaddal Saifuddin (T.U.S), Sadic Ali and Samina Ibramugi
          </p>
          <p>
            take immense pleasure in inviting you to bless & grace the occasion
            of the wedding ceremony of their son: <br />
          </p>
          <div>
            <p class="fancy">Amir with Sakina</p>
            <p>D/o Shabbir & Nafisa Modi</p>
          </div>
          <div>
            <p>With the blessings of:</p>
            <div class="flex flexcols">
              <div class="col-left">
                <p>Late Rashida Daudali Ibramugi</p>
                <p>Late Hafiza Ayub Ali Multanwala</p>
                <p>Brother and Sisters and Sister-in-Law</p>
              </div>
              <div class="col-right">
                <p>Late Daudali Ibramugi</p>
                <p>Late Sk Ayub Ali Multanwala</p>
                <p>Nieces and Nephews</p>
              </div>
            </div>
          </div>
          <div class="flex flexcols">
            <div class="col-left">
              <p>No Box Gifts</p>
            </div>
            <div class="col-right">
              <p>R.S.V.P.</p>
              <p>03368253985</p>
              <p>03008253985</p>
            </div>
          </div>
        </div>
      </div>
      <div class="page-3 page fancy">
        “Marriage <br />
        is an act of<br />
        Deen. There in<br />
        are to be found<br />
        the fruits of<br />
        good deeds<br />
        and bliss.”
      </div>
      <div class="page-4 page">
        <CardScroll/>
      </div>
    </div>
¨  </div>
</template>

<script>
import HamburgerMenu from "../components/HamburgerMenu.vue"
export default {
    name: "IndexPage",
    data() {
        return {
            opts: {
                start: 0,
                dir: "v",
                duration: 500,
                beforeChange(currentSlideEl, currenIndex, nextIndex) { },
                afterChange(currentSlideEl, currenIndex) { },
            },
        };
    },
    methods: {
        moveNext() {
            this.$refs.webpages.$fullpage.moveNext();
        },
        moveTo(to) {
            this.$refs.webpages.$fullpage.moveTo(to,true,true)
          console.log('to', to)
        }
    },
    components: { HamburgerMenu }
}
</script>
<style>
.fullpage-container {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
}
.page {
  display: flex;
  justify-content: center;
  align-items: center;
}
.page-1 {
  background: linear-gradient(-45deg, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  background-size: 400% 400%;
  animation: gradient 15s ease infinite;
  color: #ffffff;
}
.page-4 {
    background-color: #f7f8fc;
  color: #10182f;

}
.part {
  padding: 1rem 0.65rem;
  text-align: center;
}
.part-1 {
  display: flex;
  justify-content: center;
  align-items: center;
}
.part-2 {
  font-size: 0.875rem;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  background: #ffffff;
  width: 88%;
  max-width: 500px;
  height: 88vh;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.15), 0 2px 2px rgba(0, 0, 0, 0.15),
    0 4px 4px rgba(0, 0, 0, 0.15), 0 8px 8px rgba(0, 0, 0, 0.15),
    0 16px 16px rgba(0, 0, 0, 0.15), 0 32px 32px rgba(0, 0, 0, 0.15),
    inset 0 0 2px #000000;
  border-radius: 1rem;
}
.page-2 {
  background: url('/background.jpg');
  background-position: center;
  background-size: cover;
  color: #000099;
}
.page-3 {
  background: url('/back3.jpg');
  background-position: center;
  background-size: cover;
  color: #ad974f;
  align-items: flex-start;
  padding: 3rem 2rem;
}
.yellow {
  color: #ad974f;
  font-size: 1.1rem;
}
.fancy {
  color: #ad974f;
  font-size: 3rem;
  font-family: Corinthia;
  font-weight: 700;
  line-height: 3rem;
}
.page-3.fancy {
  font-size: 3.3rem;
}
.part-2 p.fancy {
  line-height: 2.5rem;
}
.flexcols {
  justify-content: space-between;
  display: flex;
  font-size: 0.75rem;
}
.col-left {
  text-align: left;
}
.col-right {
  text-align: right;
}
h1 {
  color: #ffffff;
  font-size: 7rem;
  font-family: Corinthia;
  font-weight: 700;
  line-height: 6rem;
  z-index: 11;
}
h2 {
  color: #ffffff;
  font-size: 4rem;
  font-family: Corinthia;
  font-weight: 700;
  line-height: 3rem;
  z-index: 11;
}
.down {
  position: absolute;
  bottom: 0;
  margin: 0 auto;
}
@media only screen and (min-width: 600px) {
  .part {
    padding: 2rem 2rem;
  }
  .yellow {
    font-size: 1.8rem;
  }
}
@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}
.hearts {
  width: 5%;
  min-width: 200px;
  height: 25%;
  min-height: 350px;
  position: absolute;
  z-index: 10;
}

.heart {
  position: absolute;
  height: 20%;
  min-height: 25px;
  width: 20%;
  min-width: 25px;
  background-color: red;
  -webkit-mask-image: url('data:image/svg+xml;charset=UTF-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M462.3 62.6C407.5 15.9 326 24.3 275.7 76.2L256 96.5l-19.7-20.3C186.1 24.3 104.5 15.9 49.7 62.6c-62.8 53.6-66.1 149.8-9.9 207.9l193.5 199.8c12.5 12.9 32.8 12.9 45.3 0l193.5-199.8c56.3-58.1 53-154.3-9.8-207.9z"></path></svg>');
  mask-image: url('data:image/svg+xml;charset=UTF-8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path fill="currentColor" d="M462.3 62.6C407.5 15.9 326 24.3 275.7 76.2L256 96.5l-19.7-20.3C186.1 24.3 104.5 15.9 49.7 62.6c-62.8 53.6-66.1 149.8-9.9 207.9l193.5 199.8c12.5 12.9 32.8 12.9 45.3 0l193.5-199.8c56.3-58.1 53-154.3-9.8-207.9z"></path></svg>');
  -webkit-mask-repeat: no-repeat;
  mask-repeat: no-repeat;
  -webkit-mask-position: bottom;
  mask-position: bottom;
  opacity: 0;
  animation: floating-heart 10s infinite cubic-bezier(0.5, 0.5, 0.5, 0.5);
}

@keyframes floating-heart {
  0% {
    opacity: 0;
    bottom: 0%;
    left: 0%;
  }
  10% {
    opacity: 1;
    bottom: 20%;
    left: 70%;
  }
  20% {
    bottom: 40%;
    left: 10%;
  }
  30% {
    bottom: 60%;
    left: 50%;
  }
  40% {
    opacity: 1;
    bottom: 80%;
    left: 5%;
  }
  48% {
    opacity: 0;
    bottom: 100%;
    left: 60%;
  }
  100% {
    opacity: 0;
    bottom: 100%;
    left: 90%;
  }
}

.heart:nth-child(1) {
  animation-delay: 1s;
}

.heart:nth-child(2) {
  animation-delay: 2.5s;
}

.heart:nth-child(3) {
  animation-delay: 3.5s;
}

.heart:nth-child(4) {
  animation-delay: 4.5s;
}
</style>
