<template>
  <div class="fullpage-container">
    <div ref="example" v-fullpage="opts" class="fullpage-wp">
      <div class="page-1 page">
        <div class="part part-1 fancy">
          <div>
            <p v-animate="{ value: 'bounceInLeft', delay: 300 }" class="part-3">
              Amir
            </p>
            <p
              v-animate="{ value: 'bounceInRight', delay: 900 }"
              class="part-3"
            >
              &
            </p>
            <p v-animate="{ value: 'zoomIn', delay: 1500 }" class="part-3">
              Sakina
            </p>
          </div>
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
            <p class="fancy">Amir</p>
            <p class="">with</p>
            <p class="fancy">Sakina</p>
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
“Marriage <br>
is an act of<br>
Deen. There in<br>
are to be found<br>
the fruits of<br>
good deeds<br>
and bliss.”      </div>
    </div>
    <button @click="moveNext">next</button>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      opts: {
        start: 0,
        dir: 'v',
        duration: 500,
        beforeChange(currentSlideEl, currenIndex, nextIndex) {},
        afterChange(currentSlideEl, currenIndex) {},
      },
    }
  },
  methods: {
    moveNext() {
      this.$refs.example.$fullpage.moveNext()
    },
  },
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
.page-1, .page-3 {
  background: -webkit-linear-gradient(360deg, #1c1c1c 10%, #494949 360%);
  background: -moz-linear-gradient(360deg, #1c1c1c 10%, #494949 360%);
  background: linear-gradient(360deg, #1c1c1c 10%, #494949 360%);
}
.part {
  background: #ffffff;
  text-align: center;
  width: 88%;
  max-width: 500px;
  height: 88vh;
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.15), 0 2px 2px rgba(0, 0, 0, 0.15),
    0 4px 4px rgba(0, 0, 0, 0.15), 0 8px 8px rgba(0, 0, 0, 0.15),
    0 16px 16px rgba(0, 0, 0, 0.15), 0 32px 32px rgba(0, 0, 0, 0.15),
    inset 0 0 2px #000000;
  border-radius: 1rem;
  padding: 1rem 0.65rem;
}
.part-1 {
  display: flex;
  justify-content: center;
  align-items: center;
  background: url('/marble.jpg');
  background-position: center;
  background-size: cover;
}
.part-2 {
  font-size: 0.875rem;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}
.page-2 {
  background: url('/background.jpg');
  background-position: center;
  background-size: cover;
  color: #000099;
}
.yellow {
  color: #ad974f;
  font-size: 1.1rem;
}
.fancy {
  color: #ad974f;
  font-size: 4rem;
  font-family: Corinthia;
  font-weight: 700;
  line-height: 3rem;
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
.page-3 {
  padding: 3rem 2rem;
}
@media only screen and (min-width: 600px) {
  .part {
  padding: 2rem 2rem;
}
.yellow {
  font-size: 1.8rem;
}

}
</style>
