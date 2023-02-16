<template>
  <h2>{{ title }}</h2>
  <div>{{ message }}</div>
  <p>{{ bodyMessage }}</p>
  <h1 v-show="msg">content changed successfully!</h1>
  <br />
  <button v-show="btn" @click="changeContent()">Change Content</button>
  <span v-show="loader"> loading... </span>
</template>

<script>
export default {
  // const [title, setTitle] = useState("Home Page");

  data() {
    return {
      title: "Home Page",
      message: "Plese login to continue",
      bodyMessage: "This is the body message",
      msg: false,
      loader: false,
      btn: true,
    };
  },
  methods: {
    changeContent() {
      this.loader = true;
      this.title = "About Page";
      //   setTitle("About Page")
      this.message = "This is the about page";
      this.bodyMessage = "This is the body of the about page";
      this.btn = false;
      setTimeout(() => {
        this.msg = true;
        this.loader = false;
      }, 5000);
    },
  },
};
</script>

<style>
h1 {
  color: red;
}
</style>
