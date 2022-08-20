<template>
  <div>
    <button @click="image_request">Cat Image</button>
  </div>
</template>

<script>
import axios from "axios";
import Cookies from "vue-cookies";
export default {
  mounted() {
    this.cookies = Cookies.get(`selection`);
    if (this.cookies === `cat`) {
      axios
        .request({
          url: `https://aws.random.cat/meow`,
        })
        .then((response) => {
          this.image_url = response[`data`][`file`];
                this.$root.$emit(`new_display`, this.image_url);
        })
        .catch((error) => {
          error;
        });

    }
  },
  methods: {
    image_request() {
      Cookies.set(`selection`, `cat`);
            window.location.reload();

    },
  },
  data() {
    return {
      image_url: undefined,
      cookies: undefined,
    };
  },
};
</script>

<style scoped> 
 button{
    padding: 10px;
 }
</style>
