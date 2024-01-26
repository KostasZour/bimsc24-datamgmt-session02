<!-- the script is where the js code goes -->
<script setup>
import { ref } from "vue" // you need this to use ref()

let count = ref(0);
let scriptName = ref ("addTwoNumbers.gh")
let name = ref("Anna")

function increment() { 
    count.value++;

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

            <div id="sidebar" class="center">

                <button @click="increment">Chnage Color</button>

            </div>


        </div>

        <div id="main" class="container"> Main Area 
            <p style= "margin-left: 20px" >Count is: {{count}}</p>

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


}

.center {
  width: 100%;
  padding: 30px;
  line-height: 100px;
  text-align: center;
}

#main{
    width: 75%;
    border-color: green;
    background-color: rgb(122, 202, 216);

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

.container{

    border-style: dotted;
    border-width: 1px;

}


</style>