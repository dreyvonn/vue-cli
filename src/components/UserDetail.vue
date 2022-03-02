<template>
    <div class="component">
        <h3>You may view the User Details here</h3>
        <p>Many Details</p>
        <p>User Name: {{ switchName() }}</p>
        <p>User age: {{ userAge }}</p>
        <button @click="resetFn">reset</button>
    </div>
</template>

<script>
import { eventBus } from '../main';

export default {
    props: {
        name: {
            type: String
        },
        resetFn: Function,
        userAge: {
            type: Number
        }
    },
    methods: {
        switchName() {
            return this.name.split("").reverse().join("");
        },
        resetName() {
            this.name = 'Sam';
            this.$emit('nameWasReset', this.name);
        }
    },
    created() {
        eventBus.$on('ageWasEdited', (data) => {
            this.userAge = data; 
        });
    }
}
</script>

<style scoped>
    div {
        background-color: lightcoral;
    }
</style>
