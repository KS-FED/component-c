<template>
    <div>
        <h2>tree</h2>
        <ul>
            <!-- <loop :val.sync="data" sub="children"></loop> -->
            <loop :val.sync="item" v-for="item in data" sub="children"></loop>
        </ul>
    </div>
</template>
<script type="text/javascript">
    export default {
        data (){
            return {
                data:[
                    {label:'功能',checked:true,
                    children:[
                        {label:'门店',checked:true,
                        children:[
                            {label:'查询',checked:true},    
                            {label:'编辑',checked:true}
                        ]},
                        {label:'营销',checked:true},
                        {label:'会员卡',checked:true},
                        {label:'储值卡',checked:true},
                        {label:'积分卡',checked:true},
                        {label:'现金红包',checked:true}
                    ]},
                    {label:'管理',checked:true,
                    children:[
                        {label:'会员管理',checked:true},
                        {label:'财务对账',checked:true}
                    ]},
                    {label:'设置',checked:true,
                    children:[
                        {label:'基本设置',checked:true},
                        {label:'安全中心',checked:true}
                    ]}
                ]
            }
        },
        watch:{
            // 'data':{
            //     deep:true,
            //     handler(val){
            //         console.log(val)
            //     }

            // }
        },
        ready (){
        }
    }
</script>