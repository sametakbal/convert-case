<template>
  <div class="container">
    <h1>Convert Case</h1>
    <div class="form-group">
      <textarea
        class="form-control"
        v-model="text"
        id="text"
        rows="5"
      ></textarea>
      <button
        v-for="(item, index) in buttons"
        v-bind:key="index"
        type="button"
        class="btn btn-dark"
        @click="item.action"
      >
        {{ item.title }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomeComponent",
  data() {
    return {
      text: "",
      buttons: [
        { title: "UPPER CASE", action: this.upperCaseText },
        { title: "lower case", action: this.lowerCaseText },
        { title: "Capitalize Case", action: this.capitalizeText },
      ],
    };
  },
  methods: {
    upperCaseText() {
      if (this.text) {
        this.text = this.text.toUpperCase();
      }
    },
    lowerCaseText() {
      if (this.text) {
        this.text = this.text.toLowerCase();
      }
    },
    capitalizeText() {
      if (this.text) {
        const words = this.text.split(" ");

        for (let i = 0; i < words.length; i++) {
          words[i] = words[i][0].toUpperCase() + words[i].substr(1);
        }
        this.text = words.join(" ");
      }
    },
  },
};
</script>
<style scoped>
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.container {
  background-color: rgb(106, 106, 106);
  min-height: 100vh;
}
.vertical-center {
  margin: 0;
  position: absolute;
  top: 50%;
  -ms-transform: translateY(-50%);
  transform: translateY(-50%);
}
</style>
