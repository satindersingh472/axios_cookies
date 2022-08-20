<template>
  <div>
    <button @click="image_request">Dog Image</button>
  </div>
</template>

<script>
import axios from "axios";
import Cookies from "vue-cookies";
export default {
  mounted() {
    this.cookies = Cookies.get(`selection`);
    if (this.cookies === `dog`) {
      this.image_request();

    }
  },
  methods: {
    image_request() {
    axios
        .request({
          url: `https://dog.ceo/api/breeds/image/random`,
        })
        .then((response) => {
          this.image_url = response[`data`][`message`];
                this.$root.$emit(`new_display`, this.image_url);
                  Cookies.set(`selection`, `dog`);
        })
        .catch((error) => {
          error;
        });

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
