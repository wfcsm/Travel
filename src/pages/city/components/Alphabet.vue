<template>
    <ul class="list" >
        <li class="item" v-for=" item  of letters" :key="item" @click="handlerClick" 
            @touchstart="handleTouchStart" @touchmove="handleTouchMove" @touchend="handleTouchEnd"
            :ref="item">
            {{ item }}
        </li>  
    </ul>
</template>

<script>
export default {
   name: 'CityAlphabet',
   props: {
      alpabet:Object
   },
   data(){
       return {
           touchStatus: false,
           startY: 0,
           timer: null
       }
   },
   updated () {
       this.starty = this.$refs['A'][0].offsetTop
   },
   computed: {
       letters() {
           let letters = []
           for (let i in this.alpabet){
               letters.push(i)
           }
           return letters
       }
   },
   methods: {
       handlerClick(e){
           this.$emit("change",e.target.innerText);
       },
       handleTouchStart(){
           this.touchStatus = true;

       },
       handleTouchMove(e){
            if(this.timer){
                clearTimeout(this.timer)
            }
            this.timer = setTimeout(()=>{
                const touchY = e.touches[0].clientY -79
                const index =Math.floor((touchY - this.startY)/20)
                if ( index >=0 && index <this.letters.length){
                    this.$emit('change',this.letters[index])
                }
            },16)
           
           
       },
       handleTouchEnd(){
           this.touchStatus = false;
       }
   }
}
</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
    .list
        position absolute
        top: 1.58rem
        right: 0
        bottom: 0
        width: .4rem
        display: flex
        flex-direction:column
        justify-content center
        .item
           line-height: .44rem
           text-align: center
           color: $bgColor 
       
</style>
