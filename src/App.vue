<template>
  <main>
    <div v-if="openModal"  class="overlay">
      <div class="modal">
        <textarea v-model="newNote" name="note" id="note" cols="30" rows="10"></textarea>
        <button @click="addNote()">Add Note</button>
        <button @click="openModal = false" class="close">Close</button>
        <!-- {{ newNote }} -->
      </div>
    </div>
    <div class="container">
      <header>
        <!-- {{ notes }} -->
        <h1>Notes</h1>
        <button @click="openModal = true">+</button>
      </header>
      <div class="cards-container">
         <div v-for="note in notes" :key="note.id" :style="{ backgroundColor: note.backgroundColor }" class="card">
          <p class="main-text">{{ note.text }}</p>
          <p class="date">{{ note.date }}</p>
         </div>
      </div>
    </div>
  </main>
  
</template>

<style scoped>
main{
  height: 100vh;
  width: 100vw;
  background-color: blanchedalmond
}

.container{
  max-width: 1000px;
  padding: 10px;
  margin: 0 auto;
}

header{
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h1{
  font-weight: bold;
  margin-bottom: 25px;
  font-size: 75px;
  color: black;
}

p{
  color: black;
}

.date{
  font-size: 12.5px;
}

.cards-container{
  display: flex;
  flex-wrap: wrap;
}

header button{
  border:none;
  padding: 10px;
  width: 50px;
  height: 50px;
  cursor: pointer;
  border-radius: 100%;
  color: white;
  font-size: 20px;
  background-color: rgb(21,20,20);
}

.card{
  width: 225px;
  height: 225px;
  background-color: rgb(237,182,44);
  padding: 10px;
  border-radius: 25px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-right: 20px;
  margin-bottom: 20px;
}

.overlay{
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.77);
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;
}

.modal{
  width: 750px;
  background-color: white;
  border-radius: 10px;
  padding: 30px;
  position: relative;
  display: flex;
  flex-direction: column;
}

.modal button {
  padding: 10px 20px;
  font-size: 20px;
  width: 100%;
  background-color: blueviolet;
  border: none;
  color: white;
  cursor: pointer;
  margin-top: 50px;
}

.modal .close{
  background-color: rgb(203, 9, 9);
  margin-top: 7px;
}

</style>

<script setup>
import { ref } from 'vue';

const openModal = ref(false)

const newNote = ref("")

const notes = ref([])

const lightColor= () => {
  let color = 'hsl('+Math.floor(Math.random()*361)+',50%,75%)';
  return color
}

const addNote = () => {

  if(newNote.value.length > 0){
      notes.value.push({
        id: Math.floor(Math.random()*1000000),
        text: newNote.value,
        date: new Date().toLocaleDateString('en-US', { month: '2-digit', day: '2-digit', year: 'numeric' }),
        backgroundColor: lightColor()
    })
  }

  openModal.value = false
  newNote.value = ""
}




</script>