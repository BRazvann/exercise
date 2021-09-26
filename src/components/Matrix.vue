<template>
    <button @click="setButton(0)">{{default_array[0]}}</button>
    <button @click="setButton(1)">{{default_array[1]}}</button>
    <button @click="setButton(2)">{{default_array[2]}}</button>
    <button @click="setButton(3)">{{default_array[3]}}</button>
    <br>
    <button @click="setButton(4)">{{default_array[4]}}</button>
    <button @click="setButton(5)">{{default_array[5]}}</button>
    <button @click="setButton(6)">{{default_array[6]}}</button>
    <button @click="setButton(7)">{{default_array[7]}}</button>
    <br>
    <button @click="setButton(8)">{{default_array[8]}}</button>
    <button @click="setButton(9)">{{default_array[9]}}</button>
    <button @click="setButton(10)">{{default_array[10]}}</button>
    <button @click="setButton(11)">{{default_array[11]}}</button>
    <br>
    <button @click="setButton(12)">{{default_array[12]}}</button>
    <button @click="setButton(13)">{{default_array[13]}}</button>
    <button @click="setButton(14)">{{default_array[14]}}</button>
    <button @click="setButton(15)">{{default_array[15]}}</button>
</template>

<script>
export default {
    data() {
        return {
            default_array: ['?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?', '?'],
            counter: 0,           
        }
    },

    props: ['result_modulo_2'],

    methods: {
        setButton: function(index){
            if(this.counter < this.result_modulo_2.length){
                this.default_array[index]=this.result_modulo_2[this.counter];
                this.counter+=1;
            }else{
                alert('No more values to show!');
            }
        }
    }
}
</script>

<style scoped>
    button {
        width: 60px;
        height: 60px;
        margin: 5px;
    }
</style>