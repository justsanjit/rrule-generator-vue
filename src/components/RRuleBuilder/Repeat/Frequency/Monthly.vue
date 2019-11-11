<template>
    <div class="is-inline-flex">
        <label class="label">every</label>
        <input type="number" min="1" class="input is-inline"/>
        <label class="label">month(s)</label>
        <div class="select">
            <select v-model="on">
                <option value="onThe">on the</option>
                <option value="onDay">on day</option>
            </select>
        </div>
        <component :is="component" /> 
       
    </div>
</template>

<script>
import {upperFirst} from 'lodash'
import OnDay from './Month/OnDay'
import OnThe from './Month/OnThe'

export default {
    data() {
        return {
            on: 'onThe'
        }
    },
    computed: {
        component() {
            return upperFirst(this.on);
        }
    },
    components: {OnThe, OnDay}
}
</script>