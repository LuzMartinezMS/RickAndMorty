<template>
    <div>
        <h1>Mariana</h1>
        <input type="text" v-model="input">        
        <ul>
            <li v-for="(name,index) in filteredNames" v-bind:key="index">
                {{name}}
            </li>
        </ul>    
    </div>
</template>

<script>
export default{
    name:"userName",
    data(){
        return {
            names: [
            'Parth',
            'Eduard',
            'Frank',
            'Edgar',
            'Max',
            'Chencho',
            'Demian',
            'Alexis',
            'Citlali',
            'Luz',
            'Juan'
            ],
            input:''
        }
    },
    computed:{
        filteredNames(){
            return this.input !== '' ? this.names.filter(name => name.toLowerCase().includes(this.input.toLowerCase())): ''
        }
    }

}

//let names=[
//    'Parth',
//    'Eduard',
//    'Frank',
//    'Edgar',
//    'Max',
//    'Chencho',
//    'Demias',
//    'Alexis',
//    'Citlali',
//    'Luz',
//    'Juan'
//]
</script>

<style scoped>

div{
    background: linear-gradient(#f69d3c, #641d75);
    width: 100vw;
    height: 100vh;
}
h1{
    padding-top: 30px;
    text-shadow:4px 1px 0px rgb(205, 121, 4);
    margin-top: 0px;
    color: white;

}

input{

    border-radius: 30px;
    height: 30px;
    font-weight: bold;
    text-align: center;

}

li{
    justify-items: center;
    align-items: center;
    background-color: white;
    font-size: 20px;
    color:#641d75;
    font-weight: bold;
    list-style-type: none;
    border: #641d75;
    -webkit-box-shadow: 2px 2px 2px 1px rgb(231, 227, 233);
    width: 100px;
    height: 40px;
    border-radius: 20px;
    margin-top: 10px;
}


</style>