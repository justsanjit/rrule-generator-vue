<template>
    <div class="is-inline-flex">
        <label class="label">every</label>
        <input type="number" min="1" v-model.number="interval" class="input is-inline"/>
        <label class="label">day(s)</label>
    </div>
</template>

<script>
export default {
    data() {
        return {
            interval: 1,
        }
    },
    watch: {
        interval: 'emitEvent'
    },
    methods: {
        emitEvent() {
            this.$emit('input', {
                interval: this.interval
            })
        }
    }
}
</script>