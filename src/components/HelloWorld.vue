<template>
  <div class="row">
    <div class="col-sm-12 text-center" style="padding:10px;">
      <div class="form-group">
        <label>Test Model</label>
        <input class="form-control" v-model="testModel">
        <p v-bind:class="classObject">{{reversed}}</p>
      </div>
      <button class="btn btn-dark" v-on:click="addNew()">Nouvel item</button>
    </div>
    <div class="col-sm-10 offset-sm-1">
      <ul class="list-group">
        <li class="list-group-item" v-for="(u, index) in users" :key="index">
          <strong>{{u.name}}</strong>
          <button class="btn btn-danger float-right" @click="remove(index)">Supprimer</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      users: [
        { name: "Item 1", id: 1 },
        { name: "Item 2", id: 2 },
        { name: "Item 3", id: 3 },
        { name: "Item 4", id: 4 },
        { name: "Item 5", id: 5 },
        { name: "Item 6", id: 6 }
      ],
      testBoolean: false,
      testModel: "",
      classObject:{
        'text-danger':true
      }
    };
  },
  methods: {
    reverse: function(arr) {
      arr = arr.reverse();
    },
    remove: function(index) {
      this.users.splice(index, 1);
<<<<<<< HEAD
=======
    },
    addNew: function() {
      let id = Math.ceil(Math.random() * 100);

      this.users.push({
        name: "Item " + id,
        id: id
      });

      this.users = this.users.sort((a, b) => {
        return a.id - b.id;
      });
    }
  },
  computed: {
    reversed: {
      get: function() {
        return this.testModel
          .split("")
          .reverse()
          .join("");
      },
      set: function(newValue) {
        this.testModel = newValue.toUppercase();
      }
>>>>>>> d57a50e9cbddd6dafba6a75e1d26878af8f64b1d
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
