<template>
  <div
    class="flex flex-col justify-center items-center min-h-screen min-w-screen bg-gray-900 text-white"
  >
    <div
      class="clock border border-teal-400 shadow-lg w-64 h-64 rounded-full bg-white border border-black flex flex-col justify-center items-end transform relative text-black"
    >
      <div class="number number1">1</div>
      <div class="number number2">2</div>
      <div class="number number3">3</div>
      <div class="number number4">4</div>
      <div class="number number5">5</div>
      <div class="number number6">6</div>
      <div class="number number7">7</div>
      <div class="number number8">8</div>
      <div class="number number9">9</div>
      <div class="number number10">10</div>
      <div class="number number11">11</div>
      <div class="number number12">12</div>
      <span class="center w-4 h-4 block bg-black self-center rounded-full z-50 -mb-1"></span>
      <span class="hours w-full h-1 flex justify-end -mt-1">
        <span class="hours-hand block bg-black w-32 rounded" />
      </span>
      <span class="minutes w-full h-1 flex justify-end -mt-1">
        <span class="minutes-hand block bg-blue-400 w-32 pr-6 rounded" />
      </span>
      <span class="seconds w-full h-1 flex justify-end -mt-1">
        <span class="seconds-hand block bg-red-400 w-32 rounded" />
      </span>
    </div>
    <div class="digital text-white mt-6 flex">
      <div class="flex flex-col items-center mr-4">
        <span>{{ this.date.getHours() }}</span>
        <span>HOURS</span>
      </div>
      <div class="flex flex-col items-center mr-4">
        <span>{{ this.date.getMinutes() }}</span>
        <span>MINUTES</span>
      </div>
      <div class="flex flex-col items-center">
        <span>{{ this.date.getSeconds() }}</span>
        <span>SECONDS</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Countdown",
  data() {
    return {
      date: new Date()
    };
  },
  methods: {
    clock() {
      setInterval(() => {
        this.date = new Date()
        this.seconds();
        this.minutes();
        this.hours();
      }, 1000);
    },
    hours() {
      document.querySelector(".hours").style.transform = `rotate(${
        (new Date().getHours() * 6) - 90
      }deg)`;
    },
    minutes() {
      document.querySelector(".minutes").style.transform = `rotate(${
        (new Date().getMinutes() * 6) - 90
      }deg)`;
    },
    seconds() {
      document.querySelector(".seconds").style.transform = `rotate(${
        (new Date().getSeconds() * 6) - 90
      }deg)`;
    },
  },
  mounted() {
    this.clock();
  },
};
</script>

<style>
.minutes-hand { height: 5px;}
.hours-hand { height: 6px;}
.seconds-hand { height: 3px;}
.number {
  --rotation: 0;
  position: absolute;
  width: 100%;
  height: 100%;
  text-align: center;
  transform: rotate(var(--rotation));
}
.number1 {
  --rotation: 30deg;
}
.number2 {
  --rotation: 60deg;
}
.number3 {
  --rotation: 90deg;
}
.number4 {
  --rotation: 120deg;
}
.number5 {
  --rotation: 150deg;
}
.number6 {
  --rotation: 180deg;
}
.number7 {
  --rotation: 210deg;
}
.number8 {
  --rotation: 240deg;
}
.number9 {
  --rotation: 270deg;
}
.number10 {
  --rotation: 300deg;
}
.number11 {
  --rotation: 330deg;
}
</style>
