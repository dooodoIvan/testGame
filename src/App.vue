<template>
  <div>
    <table class="blocks">
      <tr>
        <th class="redBlock" @click="clickBlock(0)"></th>
        <th class="blueBlock" @click="clickBlock(1)"></th>
      </tr>
      <tr>
        <td class="yellowBlock" @click="clickBlock(2)"></td>
        <td class="greenBlock" @click="clickBlock(3)"></td>
      </tr>
    </table>
    <div>
      <p>level</p>
      <select name="level" id="level">
        <option value="eazy">eazy</option>
        <option value="hard">hard</option>
      </select>
    </div>
    <button @click="start()">Start</button>
    <h1>{{ randomNumber }}</h1>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      mySequence: [],
      randomSequence: [],
      randomNumber: null,
    };
  },
  methods: {
    clickBlock(num) {
      this.mySequence.push(num);
      if (this.mySequence === this.randomSequence) {
        this.start();
      }
    },
    start() {
      this.randomNumber = Math.round(Math.random() * 3);
      return this.randomSequence.push(this.randomNumber);
    },
  },
};
</script>

<style lang="scss">
.blocks {
  width: 400px;
  height: 400px;
}

.redBlock {
  width: 100px;
  height: 100px;
  background-color: rgba(255, 0, 0, 0.411);
}

.redBlock:active {
  background-color: red;
}

.blueBlock {
  width: 100px;
  height: 100px;
  background-color: rgba(0, 0, 255, 0.493);
}

.blueBlock:active {
  background-color: blue;
}

.yellowBlock {
  width: 100px;
  height: 100px;
  background-color: rgba(255, 255, 0, 0.37);
}

.yellowBlock:active {
  background-color: yellow;
}

.greenBlock {
  width: 100px;
  height: 100px;
  background-color: rgba(0, 128, 0, 0.459);
}

.greenBlock:active {
  background-color: green;
}
</style>
