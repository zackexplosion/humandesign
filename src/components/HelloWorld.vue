<template>
  <div>
    <ul class="buttons">
      <li
        v-for="(n, k) in 64" :key="k"
      >
        <button
          @click="() => change(k)">{{ n }}</button>
      </li>
    </ul>
    <hr />
    <p class="content">{{ text }}</p>
  </div>
</template>

<script>
import list from "../source.js";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {
    change(index) {
      this.active = index
      this.text = list[index]
    },
  },
  data() {
    return {
      active: 0,
      text: list[0],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
// button {

// }
.buttons {
  text-align: left;
  margin: 0;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  li {
    display: inline-block;
    flex: 1 0 12%; 
    // width: 40px;
    // height: 40px;
    button {
      width: 100%;
      height: 40px;
    }
  }
}
.content {
  clear: both;
  margin-top: 2em;
}

.active {
  background: #EEE;
}

p {
  
}
</style>
