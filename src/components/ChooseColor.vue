<template>
<div class="choose-color">
    <v-card flat>
        <v-card-title class="color-title">
            Choose the color of your t-shirt.
        </v-card-title>
        <v-card-content class="color-content">
            <div class="color-content">
                <v-color-picker></v-color-picker>
            </div>


        </v-card-content>
    </v-card>
</div>
</template>

<script>
    export default {
        name: "ChooseColor.vue"
    }
</script>

<style scoped>
    .color-content {
        text-align: center;
    }

</style>
