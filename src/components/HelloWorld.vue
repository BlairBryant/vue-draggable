<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class='list1'>
      <draggable v-model="list" @start='stan'>
      <p class='item' v-for="item in list" :key='item.id'>
      {{item}}
      </p>
      </draggable>
    </div>
    <div class='list2'>
      <draggable v-model="list2">
      <p class='item2' v-for="item in list2" :key='item.id'>
      {{item}}
      </p>
      </draggable>
    </div>
  </div>
</template>

<script>
import draggable from 'vuedraggable'
export default {
  components: {
    draggable
  },
  name: "HelloWorld",
  data() {
    return {
      list: [
        { id: 1, name: "hey" },
        { id: 2, name: "yo" },
        { id: 3, name: "nooo" }
      ],
      list2: [
        { id: 4, name: "tennis" },
        { id: 5, name: "ice" },
        { id: 6, name: "melty" }
      ],
      stan: () => {
        console.log('hey')
      }
    };
  },
  props: {
    msg: String
  }
};
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  display: flex;
}
.list1 {
  width: 300px;
  height: 500px;
  background: lavender;
}
.list2 {
  width: 300px;
  height: 500px;
  background: lightsalmon;
}
.item {
  background: lightgreen;
  cursor: pointer;
}
.item2 {
  background: lightcyan;
  cursor: pointer;
}

</style>
