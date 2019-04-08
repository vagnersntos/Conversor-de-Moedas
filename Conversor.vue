<template>
    <div class="Conversor">
        <h2>{{moedaA}} Para {{moedaB}}</h2>
        <input type="text" v-model="moedaA_value" :placeholder="moedaA">
        <input type="button" value="converter" v-on:click="converter">
        <h2>{{moedaB_value}}</h2>
    </div>

</template>

<script>
import { METHODS } from 'http';
import { parse } from 'path';
export default {
    name:"Conversor",
    props:["moedaA","moedaB"],
        data(){
            return{
                moedaA_value: "",
                moedaB_value: 0
            }

        },
        methods:{
            converter(){
                let de_para = this.moedaA + "_" + this.moedaB;
                let url = 'https://free.currencyconverterapi.com/api/v6/convert?apiKey=daa0239ed38eb41b9859&q='+ de_para +'&compact=y';
           
            fetch(url)
                .then(res => {
                    return res.json();
            })
                    .then(json=>{
                        let cotacao = json[de_para].val;
                        this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                        
                    });

            }
        }
};
</script>

<style scoped>
    .Conversor{
        padding: 20px;
        max-width: 300px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 2);
    }
</style>
