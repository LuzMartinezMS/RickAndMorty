
<template>


    
    <div class="main">
         

       
            <div class= "c1" v-for="character in charactors.results" :key="character.id">
                <img :src="character.image" alt="character.name"> 
                <div class="c2">
                   <p class="name"> {{ character.name }} </p>
                   <div class="dots">
                   <span class="green" id="stat" v-if="character.status == 'Alive'"></span>
                   <span class="red" id="stat" v-else-if="character.status == 'Dead'"></span>
                   <p class="status">{{character.status}} - {{character.species}}</p>
                   </div>
                    <p class="labels">Last known location:</p><br>
                    <p class="info">{{ character.location.name}}</p>
                       <p class="labels">First seen in:</p><br>
                    <p class="info">{{ character.origin.name}}</p>
                </div>


        </div>
        
    </div>

</template>

<script>
export default{
    name:"rickAndMorty",
    data(){
        return{
        charactors:[]
 
        }
    }, 

    methods: {
        callingAPI(){
            fetch("https://rickandmortyapi.com/api/character").then(res => res.json().then((data) => {
            this.charactors=data

            }))
        }
    },
    mounted() {
        this.callingAPI()
    
    }
}
</script>

<style scooped>

.main{
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    background-color: black;
    width: 100vw;
    height: 100 vh;
    margin:0px;
}


.c1{
    display: flex;
    flex-direction: row;
    background-color: rgb(60, 62, 68); 
    color: white;
    width: 48vw;
    height:25 vh;
    margin-top:10px;
    border-radius: 10px;
    margin-bottom: 10px;
    margin-left: 10px;
}

.c2{
    display: flex;
    flex-direction: column;
    flex-wrap:wrap;
    align-items: center;
}

.name{
    font-size: 25px;
    font-weight: bolder;
    margin-top:5px;
    margin-bottom:5px;
    margin-left: 10px;
}


img{
    width: 200px;
    height: 200px;
    border-radius:5px;
}

.labels{
    color:rgb(158, 158, 158);
    font-size: 12px;
    margin: 0px;

}


.status{
    font-size: 14px;
    font-weight: bolder;
    margin-left: 10px;
    margin-top: 0px;
}

.info{
font-size: 14px;
margin-top: -10px;
margin-left: 10px;
}

#stat{
    width: 10px;
    height:10px;
    border-radius: 50%;
    display: inline-block;
}


.green{
    background-color: green;
}
.red{
    background-color: red;
}

.dots{
    display: flex;
    flex-direction: row;
    justify-content:flex-start;
    margin-left: 0px;
}


</style>