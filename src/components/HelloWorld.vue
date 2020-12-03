<template>
  <div>
    <ul class="buttons">
      <li v-for="(n, k) in 64" :key="k">
        <button @click="() => change(k)">{{ n }}</button>
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
      // console.log(list[index])
      this.text = list[index];
    },
  },
  data() {
    return {
      text: "aaa",
      aaa: list,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.buttons {
  text-align: left;
  li {
    display: inline-block;
  }
}
.content {
  clear: both;
  margin-top: 2em;
}
</style>
