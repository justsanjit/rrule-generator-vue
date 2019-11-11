<template>
    <div class="is-inline-flex">
        <div class="select">
            <select v-model="on">
                <option value="onThe">on the</option>
                <option value="on">on</option>
            </select>
        </div>
        <component :is="component" /> 
       
    </div>
</template>

<script>
import {upperFirst} from 'lodash'
import On from './Yearly/On'
import OnThe from './Yearly/OnThe'

export default {
    data() {
        return {
            on: 'on'
        }
    },
    computed: {
        component() {
            return upperFirst(this.on);
        }
    },
    components: {OnThe, On}
}
</script>