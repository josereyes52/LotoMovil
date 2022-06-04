<template>
  <div class="container">
    <h1>{{msg}}</h1>
    <div class="elements">
      <span class="next-Draw"></span>
      <span class="past-Draw past-Draw1"></span>
      <span class="past-Draw past-Draw2"></span>
      <span class="past-Draw past-Draw3"></span>
      <span class="past-Draw past-Draw4"></span>
      <div class="royal3">
        <span class="circle circle-royal1"></span>
        <span class="circle circle-royal2"></span>
        <span class="circle circle-royal3"></span>
        <span class="circle circle-royal4"></span>
        <span class="circle circle-royal5"></span>
        <span class="circle circle-royal6"></span>
        <span class="circle circle-royal7"></span>
        <span class="circle circle-royal8"></span>
        <span class="circle circle-royal9"></span>
        <span class="circle circle-royal10"></span>
        <span class="circle circle-royal11"></span>
        <span class="circle circle-royal12"></span>
      </div>
      <div class="royal4">
        <span class="circle circle-royal1"></span>
        <span class="circle circle-royal2"></span>
        <span class="circle circle-royal3"></span>
        <span class="circle circle-royal4"></span>
        <span class="circle circle-royal5"></span>
        <span class="circle circle-royal6"></span>
        <span class="circle circle-royal7"></span>
        <span class="circle circle-royal8"></span>
        <span class="circle circle-royal9"></span>
        <span class="circle circle-royal10"></span>
        <span class="circle circle-royal11"></span>
        <span class="circle circle-royal12"></span>
        <span class="circle circle-royal13"></span>
        <span class="circle circle-royal14"></span>
        <span class="circle circle-royal15"></span>
        <span class="circle circle-royal16"></span>
      </div>

      <div class="result">
        <span class="circle circle-royal1"></span>
        <span class="circle circle-royal2"></span>
        <span class="circle circle-royal3"></span>
        <span class="circle circle-royal4"></span>
        <span class="circle circle-royal5"></span>
        <span class="circle circle-royal6"></span>
        <span class="circle circle-royal7"></span>
        <span class="circle circle-royal8"></span>
        <span class="circle circle-royal9"></span>
        <span class="circle circle-royal10"></span>
        <span class="circle circle-royal11"></span>
        <span class="circle circle-royal12"></span>
      </div>

      <div class="cash-three-strainght">
        <span class="cash-three1"></span>
        <span class="cash-three2"></span>
      </div>
      <div class="cash-four-strainght">
        <span class="cash-four1"></span>
        <span class="cash-four2"></span>
      </div>

      <div class="borlette">
        <span class="first-1"></span>
        <span class="first-2"></span>
        <span class="second-1"></span>
        <span class="second-2"></span>
        <span class="third-1"></span>
        <span class="third-2"></span>
      </div>

      <div class="mariage">
        <span class="first"></span>
        <span class="second"></span>

      </div>
      
      <img src="../assets/img/IT-lottery.jpeg" alt="Result">

    </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  data () {
    return {
      fast3: "",
      fast4: "",
    }
  },
  methods: {
    getResult() {
      this.getFast3()
      this.getFast4()
    },
    getFast3() {
      fetch('https://esilotto.com.ht/Loto/Consultas.php?Tipo=C3&Fecha_inicial=2022-6-4&Fecha_hasta=2022-6-4&Sorteo=0')
        .then(res => res.json())
        .then(res => {
          const fast3 = res.Detalle
          for (let i = 1; i <= 4; i++) {
            // add to this class past-Draw1 the fecha
            const pastDraw = document.querySelector(`.past-Draw${i}`)
            pastDraw.innerHTML = `${fast3[i].Sorteo} | ${fast3[i].Hora}`

            // switch case
            switch (i) {
              case 1:
                const royal1 = document.querySelector(`.circle-royal1`)
                royal1.innerHTML = `${fast3[i].Num1}`
                const royal2 = document.querySelector(`.circle-royal2`)
                royal2.innerHTML = `${fast3[i].Num2}`
                const royal3 = document.querySelector(`.circle-royal3`)
                royal3.innerHTML = `${fast3[i].Num3}`
                break;
              case 2:
                const royal4 = document.querySelector(`.circle-royal4`)
                royal4.innerHTML = `${fast3[i].Num1}`
                const royal5 = document.querySelector(`.circle-royal5`)
                royal5.innerHTML = `${fast3[i].Num2}`
                const royal6 = document.querySelector(`.circle-royal6`)
                royal6.innerHTML = `${fast3[i].Num3}`
                break;
              case 3:
                const royal7 = document.querySelector(`.circle-royal7`)
                royal7.innerHTML = `${fast3[i].Num1}`
                const royal8 = document.querySelector(`.circle-royal8`)
                royal8.innerHTML = `${fast3[i].Num2}`
                const royal9 = document.querySelector(`.circle-royal9`)
                royal9.innerHTML = `${fast3[i].Num3}`
                break;
              case 4:
                const royal10 = document.querySelector(`.circle-royal10`)
                royal10.innerHTML = `${fast3[i].Num1}`
                const royal11 = document.querySelector(`.circle-royal11`)
                royal11.innerHTML = `${fast3[i].Num2}`
                const royal12 = document.querySelector(`.circle-royal12`)
                royal12.innerHTML = `${fast3[i].Num3}`
            }
          }
        })
        .catch(err => console.log(err))
    },
    getFast4() {
      fetch('https://esilotto.com.ht/Loto/Consultas.php?Tipo=P4&Fecha_inicial=2022-6-4&Fecha_hasta=2022-6-4&Sorteo=0')
        .then(res => res.json())
        .then(res => {
          const fast4 = res.Detalle
          for (let i = 1; i <= 4; i++) {
            // add to this class past-Draw1 the fecha
            const pastDraw = document.querySelector(`.past-Draw${i}`)
            pastDraw.innerHTML = `${fast4[i].Sorteo} | ${fast4[i].Hora}`

            // switch case
            switch (i) {
              case 1:
                const royal1 = document.querySelector(`.royal4 .circle-royal1`)
                royal1.innerHTML = `${fast4[i].Num1}`
                const royal2 = document.querySelector(`.royal4 .circle-royal2`)
                royal2.innerHTML = `${fast4[i].Num2}`
                const royal3 = document.querySelector(`.royal4 .circle-royal3`)
                royal3.innerHTML = `${fast4[i].Num3}`
                const royal4 = document.querySelector(`.royal4 .circle-royal4`)
                royal4.innerHTML = `${fast4[i].Num4}`
                break;
              case 2:
                const royal5 = document.querySelector(`.royal4 .circle-royal5`)
                royal5.innerHTML = `${fast4[i].Num1}`
                const royal6 = document.querySelector(`.royal4 .circle-royal6`)
                royal6.innerHTML = `${fast4[i].Num2}`
                const royal7 = document.querySelector(`.royal4 .circle-royal7`)
                royal7.innerHTML = `${fast4[i].Num3}`
                const royal8 = document.querySelector(`.royal4 .circle-royal8`)
                royal8.innerHTML = `${fast4[i].Num4}`
                break;
              case 3:
                const royal9 = document.querySelector(`.royal4 .circle-royal9`)
                royal9.innerHTML = `${fast4[i].Num1}`
                const royal10 = document.querySelector(`.royal4 .circle-royal10`)
                royal10.innerHTML = `${fast4[i].Num2}`
                const royal11 = document.querySelector(`.royal4 .circle-royal11`)
                royal11.innerHTML = `${fast4[i].Num3}`
                const royal12 = document.querySelector(`.royal4 .circle-royal12`)
                royal12.innerHTML = `${fast4[i].Num4}`
                break;
              case 4:
                const royal13 = document.querySelector(`.royal4 .circle-royal13`)
                royal13.innerHTML = `${fast4[i].Num1}`
                const royal14 = document.querySelector(`.royal4 .circle-royal14`)
                royal14.innerHTML = `${fast4[i].Num2}`
                const royal15 = document.querySelector(`.royal4 .circle-royal15`)
                royal15.innerHTML = `${fast4[i].Num3}`
                const royal16 = document.querySelector(`.royal4 .circle-royal16`)
                royal16.innerHTML = `${fast4[i].Num4}`
            }
          }
        })
        .catch(err => console.log(err))
    }
  },
  beforeMount(){
    this.getResult()
    console.log(this.fast3)
 }
}
</script>

<style scoped>
.elements {
  position: relative;
}

.elements img {
  pointer-events: none;
}

.elements span {
  /* background-color: red; */
  font-size: 21px;
  font-weight: bold;
  line-height: 49px;
}

span.past-Draw {
    color: white;
}

.next-Draw {
  width: 7.5%;
  height: 5%;
  position: absolute;
  top: 13.3%;
  left: 25%;
}
.past-Draw {
  width: 24.7%;
  height: 6%;
  left: 4%;
  position: absolute;
}
.past-Draw1 {
  top: 28.3%;
}
.past-Draw2 {
  top: 37.3%;
}
.past-Draw3 {
  top: 46%;
}
.past-Draw4 {
  top: 54.7%;
}

.circle {
  width: 4%;
  height: 7%;
  border-radius: 50%;
  position: absolute;
  
}

.royal3 .circle-royal1 {
  left: 35.34%;
  top: 28%;
}

.royal3 .circle-royal2 {
  left: 40.5%;
  top: 28%;
}

.royal3 .circle-royal3 {
  left: 45.6%;
  top: 28%;
}

.royal3 .circle-royal3 {
  left: 45.6%;
  top: 28%;
}

.royal3 .circle-royal4 {
  left: 35.34%;
  top: 36.8%;
}

.royal3 .circle-royal4 {
  left: 35.34%;
  top: 36.8%;
}

.royal3 .circle-royal5 {
  left: 40.5%;
  top: 36.8%;
}

.royal3 .circle-royal6 {
  left: 45.6%;
  top: 36.8%;
}

.royal3 .circle-royal7 {
  left: 35.4%;
  top: 45.8%;
}

.royal3 .circle-royal8 {
  left: 40.5%;
  top: 45.8%;
}

.royal3 .circle-royal9 {
  left: 45.6%;
  top: 45.8%;
}

.royal3 .circle-royal10 {
  left: 35.4%;
  top: 54.8%;
}

.royal3 .circle-royal11 {
  left: 40.5%;
  top: 55%;
}

.royal3 .circle-royal12 {
  left: 45.6%;
  top: 55%;
}

.royal4 .circle-royal1 {
  left: 54.9%;
  top: 28%;
}

.royal4 .circle-royal2 {
  left: 60%;
  top: 28%;
}

.royal4 .circle-royal3 {
  left: 65.1%;
  top: 28%;
}

.royal4 .circle-royal4 {
  left: 70.2%;
  top: 28%;
}

.royal4 .circle-royal5 {
  left: 54.9%;
  top: 36.8%;
}

.royal4 .circle-royal6 {
  left: 60%;
  top: 36.8%;
}

.royal4 .circle-royal7 {
  left: 65.1%;
  top: 36.8%;
}

.royal4 .circle-royal8 {
  left: 70.2%;
  top: 36.8%;
}

.royal4 .circle-royal9 {
  left: 54.9%;
  top: 45.8%;
}

.royal4 .circle-royal10 {
  left: 60%;
  top: 45.8%;
}

.royal4 .circle-royal11 {
  left: 65.1%;
  top: 45.8%;
}

.royal4 .circle-royal12 {
  left: 70.2%;
  top: 45.8%;
}

.royal4 .circle-royal13 {
  left: 54.9%;
  top: 54.8%;
}

.royal4 .circle-royal14 {
  left: 60%;
  top: 54.8%;
}

.royal4 .circle-royal15 {
  left: 65.1%;
  top: 54.8%;
}

.royal4 .circle-royal16 {
  left: 70.2%;
  top: 54.8%;
}

.result .circle-royal1 {
  left: 79.5%;
  top: 28%;
}

.result .circle-royal2 {
  left: 84.65%;
  top: 28%;
}

.result .circle-royal3 {
  left: 89.76%;
  top: 28%;
}

.result .circle-royal4 {
  left: 79.5%;
  top: 36.8%;
}

.result .circle-royal5 {
  left: 84.65%;
  top: 36.8%;
}

.result .circle-royal6 {
  left: 89.76%;
  top: 36.8%;
}

.result .circle-royal7 {
  left: 79.5%;
  top: 45.8%;
}

.result .circle-royal8 {
  left: 84.65%;
  top: 45.8%;
}

.result .circle-royal9 {
  left: 89.76%;
  top: 45.8%;
}

.result .circle-royal10 {
  left: 79.5%;
  top: 54.8%;
}

.result .circle-royal11 {
  left: 84.65%;
  top: 55%;
}

.result .circle-royal12 {
  left: 89.76%;
  top: 55%;
}

.cash-three-strainght span,
.cash-four-strainght span,
.borlette span,
.mariage span {
  background-color: red;
  position: absolute;
}

.borlette span,
.mariage span {
  width: 6%;
    height: 6%;
}

.borlette .first-1 {
  top: 75%;
  left: 34%;
}

.borlette .first-2 {
  top: 75%;
  left: 43%;
}

.borlette .second-1 {
  top: 82.6%;
  left: 34%;
}

.borlette .second-2 {
  top: 82.6%;
  left: 43%;
}

.borlette .third-1 {
  top: 90.5%;
  left: 34%;
}

.borlette .third-2 {
  top: 90.5%;
  left: 43%;
}

.mariage .first {
  top: 75%;
  left: 52.8%;
}

.mariage .second {
  top: 75%;
  left: 61.2%;
}



.cash-three1 {
  left: 3.6%;
  top: 75%;
  width: 10%;
  height: 6%;
}
.cash-three2 {
  left: 18.6%;
  top: 75%;
  height: 6%;
  width: 5.6%;
}

.cash-four1 {
  left: 3.6%;
  top: 90.3%;
  width: 10%;
  height: 6%;
}

.cash-four2 {
  left: 18.6%;
  top: 90.3%;
  height: 6%;
  width: 5.6%;
}

img {
  width: 100%;
  height: auto;
}
</style>
