<template>
    <div class="is-inline">
        <label class="label is-inline">Repeat </label>
        <div class="select">
            <select @change="handleFrequency" :value="frequency">
                <option value="daily">Daily</option>
                <option value="weekly">Weekly</option>
                <option value="monthly">Monthly</option>
                <option value="yearly">Yearly</option>
            </select>
        </div>
        <component :is="component" @input="handleInputChange"/>
    </div>
</template>

<script>
import {camelCase, capitalize} from 'lodash'
import Daily from './Frequency/Daily'
import Weekly from './Frequency/Weekly'
import Monthly from './Frequency/Monthly'
import Yearly from './Frequency/Yearly'


export default {
    data() {
        return {
            frequency: 'daily',
            input: {}
        }
    },
    computed:{
        component() {
            return capitalize(camelCase(this.frequency));
        }
    },
    methods: {
        handleFrequency(event) {
            this.freq = event.target.value
            this.emitEvent();
        },
        handleInputChange(obj) {
            this.input = obj
            this.emitEvent();
        },
        emitEvent() {
            this.$emit('input', Object.assign(this.input, {
                freq: this.frequency
            }))
        }

    },
    components: {Daily, Weekly, Monthly, Yearly}
}
</script>