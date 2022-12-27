<script>
import Checkbox from './checkbox.vue';

export default {
  components: { Checkbox },
 
  data() {
    return {
      itemToDo: [],
      text: "",
     
    };
  },
  methods: {
    addToDo() {
      this.itemToDo.push(this.text);
    },
    deleteToDo(index) {
      this.itemToDo.splice(index, 1);
    },
   handleConsole(){
    console.log("oi")
   }
  },
};

 
</script>

<template >
  <div class="container">
    <div class="inputButtonContainer">
      <input class="input" v-model="text" />
      <button class="button" @click="addToDo">Adicionar</button>
    </div>
    <div
      v-for="(item, index) in itemToDo"
      v-bind:key="index"
      class="containerItems"
    >
      <div class="containerCheckboxText">
        <Checkbox :click="handleConsole" />
        <h3>{{ item }}</h3>
      </div>
      <button @click="deleteToDo(index)" class="buttonDelete">X</button>
    </div>
  </div>
</template>

<style scoped>
.input {
  border-radius: 15px;
  width: 80%;
  height: 25px;
  padding: 2px 15px;
  margin-right: 10px;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.button {
  background-color: #7f00b2;
  border-radius: 15px;
  color: white;
  font-weight: 700;
  width: 15%;
  cursor: pointer;
}
.buttonDelete {
  border-radius: 50%;
  background-color: #000000;
  color: #e42023;
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  cursor: pointer;
  padding: 10px;
  font-size: 1.5rem;
}
.buttonDelete:hover {
  color: #f264bc;
}
.button:hover {
  background-color: #f264bc;
}
.inputButtonContainer {
  display: flex;
  flex-direction: row;
  justify-content: center;
  width: 100%;
}
.containerItems {
  display: flex;
  flex-direction: row;
  width: 95%;
  padding: 2px 12px;
  align-items: center;
  justify-content: space-between;
  border-radius: 15px;
  border: 1px solid #c0c0c0;
  margin-top: 15px;
}
.containerCheckboxText {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
}
.checkboxChecked {
  height: 20px;
  width: 20px;
  margin-right: 10px;
  background-color: #7f00b2;
  border-radius: 5px;
  cursor: pointer;
}
.checkbox {
  height: 20px;
  width: 20px;
  margin-right: 10px;
  border-radius: 5px;
  border: 1px solid #0000;
  background-color: #ffff;
  cursor: pointer;
}
</style>