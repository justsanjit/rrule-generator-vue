<template>
    <div class="select">
        <select v-model="day">
            <option v-for="day in days" :key="day" :value="day">{{ day }}</option>
        </select>
    </div>
</template>

<script>
import {range} from 'lodash'

export default {
    data() {
        return {
            day: 1
        }
    },
    computed: {
        days() {
            return range(1, 32)
        }
    }
}
</script>