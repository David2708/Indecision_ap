<template>
  <h2>{{ customTitle}} </h2>
  <p>{{ counter }} <sup>2</sup> = {{ squareCounter }} </p>
  
  <button @click="increase" >+1</button>
  <button @click="decrease" >-1</button>

</template>

<script>
export default {
    // name: 'Patito',
    props: {
        title: String,
        start: {
            type: Number,
            required: true,
            default: 100,
            validator(value){
                return value >= 0
            }
        }
    },

    data(){
        return{
            counter: this.start
        }
    },

    methods:{
        getSquareValue(){
            console.log('getSquaredValue')
            return this.counter ** 2
        },
        increase(){
            this.counter++
        },
        decrease(){
            this.counter--
        }
    },

    computed: {
        squareCounter(){
            console.log('squareCounter')
            return this.counter ** 2
        },
        customTitle(){
            return this.title || 'Counter'
        }
    }

}
</script>

<style scoped>

    button{
        background-color: #64BB87;
        border-radius: 5px;
        color: white;
        cursor: pointer;
        margin: 0 5px;
        margin: 0 5px;
        transition: 0.3s ease-in-out;
    }

    button:hover {
        background-color: #5aa67b;
        transition: 0.3s ease-in-out;
    }

</style>