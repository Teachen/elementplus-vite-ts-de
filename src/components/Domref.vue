<template>
    <div>
        <div ref="myName">张三</div>
        <div :ref="goodsRefs">羊肉串</div>
        <div :ref="goodsRefs">啤酒</div>
        <div :ref="goodsRefs">花生</div>
    </div>
</template>

<script lang="ts">
import { defineComponent, nextTick, onMounted, ref } from 'vue'

export default defineComponent({
    setup() {
        let name = ref<any>(null)
        // onMounted(() => {
        //     console.log(name.value.innerHTML)
        // })
        let eleGoods:any []=[]
        nextTick(() => {
            console.log(name.value.innerHTML)
            console.log(eleGoods[0].innerHTML)
            console.log(eleGoods[1].innerHTML)
            console.log(eleGoods[2].innerHTML)
        })
        let goodsRefs=(el:any)=>{
            // console.log(eleGoods)
            eleGoods.push(el)
        }
        return {
            myName: name,
            goodsRefs
        }
    },
})
</script>
