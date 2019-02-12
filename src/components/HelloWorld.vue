<template>
  <div id="e3" style="max-width: 400px; margin: auto;" class="grey lighten-3">
    <v-card v-for="user in users" v-bind="user.id" v-bind:data="user" v-bind:key="user.text">
      <v-container fluid grid-list-lg>
        <v-layout row wrap>
          <v-flex xs12>
            <v-card color="cyan darken-2" class="white--text">
              <v-layout>
                <v-flex xs12 md12>
                  <v-img
                    :src="user.picture.large"
                    height="125px"
                    contain
                    :lazy-src="user.picture.large"
                    aspect-ratio="1"
                  ></v-img>
                </v-flex>
                <v-flex xs12 md12>
                  <v-card-title primary-title>
                    <div>
                      <div class="headline">Name: {{user.name.first}}</div>
                      <div>Email: {{user.email}}</div>
                      <div>Celphone: {{user.cell}}</div>
                      <div>Age: {{user.registered.age}}</div>
                    </div>
                  </v-card-title>
                </v-flex>
              </v-layout>
              <v-divider light></v-divider>
              <v-card-actions class="pa-3">Evaluate this user:
                <v-rating v-model="rating" background-color="orange lighten-3" color="orange"></v-rating>
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
      </v-container>
    </v-card>
  </div>
</template>

<script>
import Axios from "axios";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      users: []
    };
  },
  mounted() {
    this.getUsers();
  },
  methods: {
    getUsers() {
      Axios.get("https://randomuser.me/api/")
        .then(response => {
          this.users = response.data.results;
        })
        .catch(error => {
          alert("no se pudo cargar datos, intente nuevamente");
        });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
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
</style>
