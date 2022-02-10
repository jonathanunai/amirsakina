<template>
    <div class="row">
      <div v-if="darees" class="card">
        <div class="card-header">
          <img src="/photos/yusufi.jpg" alt="DAREES" />
        </div>
        <div class="card-body">
          <span class="tag tag-teal">21st FEBRUARY</span>
          <h3>Darees</h3>
          <p>8pm</p>
          <h4>Yusufi Masjid</h4>
          <p>Shabbirabad Block B, Karachi</p>
        </div>
      </div>
      <div v-if="dulhandarees" class="card">
        <div class="card-header">
          <img src="/photos/dulhan-darees.jpeg" alt="DAREES" />
        </div>
        <div class="card-body">
          <span class="tag tag-teal">22nd FEBRUARY</span>
          <h3>Dulhan Darees</h3>
          <p>8pm</p>
          <h4></h4>
          <p>38A Syedna Zoeb Rd Shabbirabad Block A, Karachi</p>
        </div>
      </div>
      <div v-if="mehendi" class="card">
        <div class="card-header">
          <img src="/mehendi.jpeg" alt="Mehendi" />
        </div>
        <div class="card-body">
          <span class="tag tag-pink">23st FEBRUARY</span>
          <h3>Mehendi Ceremony</h3>
          <p>Location: To be confirmed</p>
        </div>
      </div>
      <div v-if="rukhasti"  class="card">
        <div class="card-header">
          <img src="/rukhsati.jpeg" alt="RUKHSATI" />
        </div>
        <div class="card-body">
          <span class="tag tag-purple">24st FEBRUARY</span>
          <h3>Rukhsati</h3>
          <p>Location: To be confirmed</p>
        </div>
      </div>
      <div v-if="walima" class="card">
        <div class="card-header">
          <img src="/walima.jpeg" alt="Walima" />
        </div>
        <div class="card-body">
          <span class="tag tag-yellow">26st FEBRUARY</span>
          <h3>Walima/reception</h3>
          <h4>Majestic Banquet Hall</h4>
          <p>
            Address: Next to Lal Qila Restaurant <br />
            Main Shahrah-e-Faisal, Karachi
          </p>
        </div>
      </div>
    </div>
</template>
<script>
export default {
  props: {
    clave: {
      type: String,
      default: ''
    },
  },
  data() {
    return {
    }
  },
  computed: {
    darees() {
      return ['amsa1877', 'love4459', 'code9661'].includes(this.clave)
    },
    dulhandarees() {
      return ['amsa1877'].includes(this.clave)
    },
    mehendi() {
      return ['amsa1877'].includes(this.clave)
    },
    rukhasti() {
      return ['amsa1877'].includes(this.clave)
    },
    walima() {
      return ['amsa1877', 'code9661', 'happy841'].includes(this.clave)
    },
  },
}
</script>
¨
<style>
.row {
  align-items: stretch;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  overflow-x: auto;
  overflow-y: hidden;
  padding: 2rem;
}
.card {
  /*float: left;*/
  margin: 10px;
  margin-bottom: 2rem;
  border: 0;
  flex-basis: 80%;
  flex-grow: 0;
  flex-shrink: 0;
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 2px 20px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  min-width: 330px;
}

.card > img {
  margin-bottom: 0.75rem;
  width: 100%;
}

.card-text {
  font-size: 85%;
}
.card-header img {
  width: 100%;
  height: 200px;
  object-fit: cover;
}
.card-body {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 20px;
  min-height: 200px;
}

.tag {
  background: #cccccc;
  border-radius: 50px;
  font-size: 12px;
  margin: 0;
  margin-bottom: 1rem;
  color: #fff;
  padding: 2px 10px;
  text-transform: uppercase;
}
.tag-teal {
  background-color: #47bcd4;
}
.tag-purple {
  background-color: #5e76bf;
}
.tag-pink {
  background-color: #cd5b9f;
}
.tag-yellow {
  background-color: #ad974f;
}
.card h3 {
  font-size: 1.5rem;
}
.card-body p {
  font-size: 13px;
  margin: 0 0 40px;
}
@media only screen and (min-width: 500px) {
  .card {
    flex-basis: 60.333%;
  }
}
@media only screen and (min-width: 600px) {
  .card {
    flex-basis: 33.333%;
  }
}
</style>
