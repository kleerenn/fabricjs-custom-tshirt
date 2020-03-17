<template>
<div class="choose-color">
    <v-card flat>
        <v-card-title class="color-title">
            Choose the color of your t-shirt.
        </v-card-title>
        <v-card-text class="color-content">
            <div class="color-content mx-auto">
                <v-color-picker show-swatches
                                v-model="color"
                                @input="selectedColor"
                ></v-color-picker>
                <p>Selected Color: {{color}}</p>
            </div>
        </v-card-text>
    </v-card>
</div>
</template>

<script>
    export default {
        name: "ChooseColor.vue",
        data() {
            return {
                color: '#FFFFFF'
            }
        },
        computed: {
        },
        methods: {
            selectedColor() {
                console.log(this.color)
                this.$emit('selectedColor', this.color)
            }
        }
    }
</script>

<style scoped>
    .color-content {
        text-align: center;
    }

</style>
