<script setup>
import { reactive } from 'vue';

 

let boards = reactive([
                            {   id: crypto.randomUUID(), 
                                name: 'Tablero 1', 
                                items: [
                                    { id: crypto.randomUUID(), title: 'Feature de archivos'}, 
                                    { id: crypto.randomUUID(), title: 'Resolver bugs'}  ],
                            },  
                            {   id: crypto.randomUUID(), 
                                name: 'Tablero 2', 
                                items: [
                                    { id: crypto.randomUUID(), title: 'Ver frontEnd'}, 
                                    { id: crypto.randomUUID(), title: 'CSS con fallas'}  ],
                            },
                            {   id: crypto.randomUUID(), 
                                name: 'Tablero 3', 
                                items: [
                                    { id: crypto.randomUUID(), title: 'Ver REST'}, 
                                    { id: crypto.randomUUID(), title: '1hr Descanso'}  ]   }   ]);

</script>


<template>
<nav>
    <ul>
       <li> <a href="#"> Create board </a> </li> 
    </ul>
</nav>

<div class="boards-container">
    <div class="boards">
        <div class="board" v-for='board in boards' :key="board.id"> 
            <div> {{board.name}} </div>
                <div class="items"> 
                    <div class="item" v-for="item in board.items" :key="item.id">
                        {{item.title}}
                    </div>
                </div>
        </div>
    </div>
</div>


</template>


<style scoped> 
.boards{
    display: flex;
    gap: 10px;
}
.board{
    background: #efefef;
    padding: 10px;
}
 .items{
    display: flex;
    flex-direction: column;
    gap:5px;
} 
.item{
    background-color: white;
    padding: 10px;
    box-sizing: border-box;
}


</style>