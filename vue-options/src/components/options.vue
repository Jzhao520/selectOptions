<template>
    <div class="box">
        <div :id="`sl_${id}`" class="input-select v-relative" ref="toggle" @mousedown="toggleDropdown($event)" @mouseleave="optionsLeave($event)">
            <div class="options-default" @click="selectOptions" :class="open?'active-animation-route':''">{{init?init:initOption}}</div>
            <div class="options-list v-absolute" id="options-list" v-if="open">
                <ul>
                    <li class="worker-status" 
                        v-for="(item,index) in list" 
                        :class="status.index == index?'worker-status-checked':''" 
                        :key="item.id"
                        :data-isAmerican="item.flag?item.flag:null"
                        :data-content="item.default"
                        :data-value ="item.value"
                        @mousedown.prevent.stop="getValue(index,$event)"
                        >
                        <slot name="item" :item="item">
                            {{item.default}}
                        </slot>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>
<script>
import uniqueId from '../utils/uniqueId'
export default {
    name :'optionComponent',
    props:{
        data :{
            type :Array
        },
        init:{
            type :[String,Boolean],
            default : "请选择"
        },
        status :{
            type : Object
        }
    },
    data(){
        return {
            open:false,
            id : uniqueId()
        }
    },
    created(){},
    computed:{
        list(){
            return this.data
        }
    },
    methods:{
        selectOptions(){
            return this.open ? true : false
        },
        toggleDropdown(event){
            const targetIsNotSearch = event.target
            if (targetIsNotSearch) {
                event.preventDefault();
            }
            if (this.selectOptions() && targetIsNotSearch) {
                this.open = false
            } else{
                this.open = true
            }
           
        },
        optionsLeave(event){
            const targetIsNotSearch = event.target
            if (targetIsNotSearch) {
                event.preventDefault();
            }
            if(this.open){
                this.open = false
            }
        },
        getValue(index,e){
            
            const _DATA_ = {
                    content : e.target.dataset.content,
                    index : index,
                    value : e.target.dataset.value?e.target.dataset.value :''
                }
            
            this.$emit('update:status',_DATA_)
            this.open = false
        }
    }
}
</script>
<style lang="sass">
    @import "../assets/sass/index"
</style>