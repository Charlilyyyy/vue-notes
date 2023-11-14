<template>
  <main>
    <div style="display: none;" class="overlay">
      <div class="modal">
        <textarea name="note" id="note" cols="30" rows="10"></textarea>
        <button>Add Note</button>
        <button class="close">Close</button>
      </div>
    </div>
    <div class="container">
      <header>
        <h1>Notes</h1>
        <button>+</button>
      </header>
      <div class="cards-container">
         <div class="card">
          <p class="main-text">Lorem, ipsum dolor sit amet consectetur adipisicing elit. Cum porro, recusandae adipisci suscipit cumque rerum.</p>
          <p class="date">22/10/2023</p>
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