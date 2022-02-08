<template>
    <div id="root">
        <h1>{{ title }}</h1>

        Precione una tecla
        <input type="text" v-on:keydown="key" >
        <!-- <p>Tecla presionada {{keycode}}</p>  -->
        <p v-show="resultado() " :style="{color: colorgreen}">Tecla presionada {{keycode}}</p>
        <p v-show="!resultado() " :style="{color: colorred}">Tecla presionada {{keycode}}</p>
        <p v-show="resultado() " :style="{color: coloryellow}">Tecla presionada {{keycode}}</p>

        <!-- no pude llamar de otra manera a la ultima condicion -->
    </div>
</template>


<script>
export default {
     name:"firstcomponent",
     data(){
         return{
             title:"Mi primer componente",
             keycode:'',
             colorgreen:'green',
             colorred:'red',
             coloryellow:"yellow"


         }
     },
     methods:{

         resultado(){
             if (this.keycode >=65 & this.keycode <=90) {
                 return true
             } else if (this.keycode >=48 & this.keycode<=57) {
                    return false  
             } else {
                return  
             } 
                 
             
         },

         key(event){
             this.keycode= event.keyCode
           
         },

         computed:{
             styleP(){
                 return{
                     color: 'blue'
                 }
             }
         }


     }
    
}
</script>