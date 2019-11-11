<template>
    <Frequency @input="handleInput"/>
</template>

<script>
import Frequency from './RRuleBuilder/Repeat/Frequency'
export default {
    name: 'Form',
    methods: {
        handleInput(event) {
            // eslint-disable-next-line no-console
            console.log(event);
        }
    },
    components: {Frequency}
}
</script>
