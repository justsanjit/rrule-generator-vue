<template>
    <div class="is-inline-flex">
        <label class="label">every</label>
        <input type="number" min="1" class="input is-inline"/>
        <label class="label">weeks(s) on </label>
        <div class="field has-addons">
            <p class="control" v-for="day in days" :key="day">
                <button
                    class="button"
                    :class="{'is-active' : isActiveDay(day)}"
                    @click="toggleDay(day)"
                >
                    {{ day }}
                </button>
            </p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selectedDays: []
        }
    },
    computed: {
        days() {
            return ['su', 'mo', 'tu', 'we', 'th', 'fr', 'sa']
        }
    },
    methods: {
        toggleDay(day) {
            const index = this.selectedDays.findIndex(d => d === day)
            if (index === -1) {
                this.selectedDays.push(day)
            } else {
                this.selectedDays = [
                    ...this.selectedDays.slice(0, index),
                    ...this.selectedDays.slice(index + 1)
                ]
            }
        },

        isActiveDay(day) {
            return this.selectedDays.some(d => d === day);
        }
    }

}
</script>