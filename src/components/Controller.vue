<template>
    <label>Enter an array containing comma separated numbers between 100 and 999:</label>
    <br>
    <input @click="clearOutput()" required v-model="array">
    <button @click='findMax(this.array)'>Calculate</button>
    <br>
    <h3>Results:</h3>
    <p>
        <span>Max-values: {{result_max}}</span>
        <br>
        <span>Modulo-values: {{result_modulo}}</span>
    </p>
    <h3 v-if='this.result_modulo.length != 0'>Matrix: </h3>
    <Matrix v-if='this.result_modulo.length != 0' v-bind:result_modulo_2="this.result_modulo"/>
    
</template>

<script>
import Matrix from './Matrix.vue'

export default {
    components: {
        Matrix
    },
    data() {
        return {
            array: [],
            result_max: [],
            result_modulo: [],
            alphabet_mapping: {
                '0': 'A',
                '1': 'B',
                '2': 'C',
                '3': 'D',
                '4': 'E',
                '5': 'F',
                '6': 'G',
                '7': 'H',
                '8': 'I',
                '9': 'J',
                '10': 'K',
                '11': 'L',
                '12': 'M',
                '13': 'N',
                '14': 'O',
                '15': 'P',
                '16': 'Q',
                '17': 'R',
                '18': 'S',
                '19': 'T',
                '20': 'U',
                '21': 'V',
                '22': 'W',
                '23': 'X',
                '24': 'Y',
                '25': 'Z',
            },            
        }
    },

    props: {
        result_modulo_2 : {
            type: Array,
            default: function(){ 
                return ['?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?']
            }
        }
    },

    methods: {
        findMax: function(array){
            let new_array = array.replace(/, +/g, ",").split(",").map(Number);
            let choice_mark = 2;
            this.array = new_array.sort((a, b) => parseInt(a, 10) - parseInt(b, 10));
            for (let i = 0; i < this.array.length-1; i++) {
                if(this.array[i] / 100 < choice_mark && this.array[i+1] / 100 >= choice_mark){
                    this.result_max.push(this.array[i]);
                    this.result_modulo.push(this.alphabet_mapping[this.array[i]%26])
                    choice_mark = this.array[i+1] / 100 + 1;
                }
            }
            this.result_max.push(this.array[this.array.length-1])
            this.result_modulo.push(this.alphabet_mapping[this.array[this.array.length-1]%26])

            if (this.array.length != 0){
                this.array = []
            }
        },

        clearOutput: function(){
            if (this.array.length === 0){
                this.result_max = []
                this.result_modulo = []
            }
        },
    }
}
</script>

<style scoped>
    input {
        margin-top: 10px;
        width: 400px;
        height: 15px;
        border-radius: 5px;
    }
    button {
        margin-left: 15px;
    }
    p {
        margin: auto;
        width: 500px;
        height: 100px;
        border-style: double;
        border-radius: 15px;
    }
</style>