<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue" // you need this to use ref()

let count = ref(0);
let scriptName = ref ("addTwoNumbers.gh")
let name = ref("Kostas")

function increment() { 
    count.value++;

}


const mainColor = ref('#ffffff'); // Initial color for the main content
const newColor = ref(''); // Variable to store the color from the text box

const changeMainColor = () => {
  // Update the mainColor with the value from the text box
  mainColor.value = newColor.value;
};


const textInput = ref('');
const textList = ref([]);

function addText() {
  textList.value.push(textInput.value);
  // Optionally, you can clear the input after adding text
  // textInput.value = '';
}


</script>


<!-- the template is where the html code goes -->
<template>
   
   <div id="navbar" class="container">  
        <div id="title">{{name}} awesome website</div>
        
        <div id="logo">
            <img src="./cow.jpg" alt="macad cow">

        </div>
        

    </div>

    <div id="flex">

        <div id="sidebar" class="container"> Sidebar 

            <div id="sidebar" class="center">

                <button @click="increment">Add one more</button>

            </div>

    

            <div class="sidebar">

                <button @click="changeMainColor">Change Main Color</button>
                <input v-model="newColor" type="text" placeholder="Enter Color" />

                <button @click="addText">Add Text</button>
                <input v-model="textInput" type="text" placeholder="Enter Text" />
                

            </div>




        </div>

        

        <div id="main" :style="{ backgroundColor: mainColor }"> Main Area 

            <p style= "margin-left: 20px" >Count is: {{count}}</p>

            <!-- Display all added texts -->
            <p v-for="(text, index) in textList" :key="index" style="margin-left: 20px">
                Text added: {{ text }}
            </p>

                
            </div>




    </div>

    
    

</template>



<!-- style is where the css code goes -->
<style scoped>
html{
    
    background-color: rgb(0, 0, 0); 
    color: rgb(250, 246, 246);
}

body{

    margin:0;
}

div{

    /* put the borders in the inside of container */
    box-sizing: border-box;
}

img{

    height: 100%;
    width: auto;

}

#navbar{

    height: 50px;
    border-color: rgb(38, 123, 219);
    background-color: rgb(101, 161, 161);


}

#flex{
    
    display: flex;
    height: calc(100vh - 50px);
}

#sidebar{
    
    width: 25%;
    border-color: rgb(38, 123, 219);
    background-color: rgb(165, 211, 224);
    padding: 20px;
    

}

.center {

  width: 200%;
  padding: 30px;
  line-height: 100px;
  
}

#main{
    width: 75%;
    border-color: green;
    background-color: var(--mainColor);
    padding: 20px;
    flex: 1;

}

#title{
    width: 70%;
    float:left;
}

#logo{
    width: 30%;
    height: 100%;
    float:right;
    text-align: right;

}

.button {
  margin-bottom: 10px;
}

.container{

    border-style: dotted;
    border-width: 1px;

}


</style>