<template>
    <div class="block" v-if="showblock" @click="endtime">
        click me!
    </div>
</template>

<script>
export default{
    props:['delay'],
    data(){
        return{
            showblock:false,
            st:0,
            et:0
            
        }
    },
    
    mounted(){
        setTimeout(()=>{
            this.showblock = true;
            this.starttime();
        },this.delay)
        
    },
    methods:{
        starttime(){
            this.st = new Date().getTime()
            console.log(this.st)
        },
        endtime(){
            this.et = new Date().getTime()
            console.log(this.et)
            console.log(this.et-this.st)
            this.$emit('endgame',this.et-this.st)
        }
    }
    
    
}
</script>

<style>
.block{
    width: 400px;
    background-color:#0faf87;
    padding: 100px 0;
    margin: 40px auto;
    border-radius: 20px;
    cursor: pointer;
    color:white;
}
</style>
