<template>
    <li>
        <div>
            <label><input type="checkbox" v-model="val.checked" v-on:change="change(val)">&nbsp;&nbsp;{{val.label}}</label>
        </div>
        <ul v-if="val[sub]">
            <loop v-for="item in val[sub]" :val="item" :sub="sub"></loop> 
        </ul>
    </li>
</template>
<script type="text/javascript">
    export default {
        name:'loop',
        props:{
            val:[],
            sub:[]
        },
        data(){
            return {

            }
        },
        computed: {
            isFolder: function () {
              return this.val[this.sub] &&
                this.val[this.sub].length
            }
        },
        methods:{
            change(val){
                // if(this.isFolder){
                //     console.log(val.checked)
                //     this.val[this.sub].forEach((sub)=>{
                //         sub.checked = val.checked
                //     })
                // }
                
            }
        },
        watch:{
            'val.checked'(checked){
                if(this.isFolder){
                    
                    this.val[this.sub].forEach((sub)=>{
                        sub.checked = checked
                    })
                }else{
                    console.log(checked)
                }
            }
        },
        created(){
            // this.val = this.val[this.sub]||this.val
            // console.log(this.val.label)
        }
    }
</script>
<style lang="scss">
    ul {
        ul {
            padding-left: 24px;
        }
    }
</style>