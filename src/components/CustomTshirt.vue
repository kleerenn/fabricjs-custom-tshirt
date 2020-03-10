<template>
    <div id="tshirt-div">
        <img id="tshirt-backgroundpicture" src="../assets/img/bg-tshirt.png"/>
        <div id="drawingArea" class="drawing-area">
            <div class="canvas-container">
                <canvas id="canvas" width="200" height="400"></canvas>
            </div>
        </div>
    </div>
</template>

<script>
    import { fabric } from 'fabric'
    export default {
        name: "CustomTshirt",
        data() {
            return {
                canvas: null

            }
        },
        beforeMount() {
             this.canvas = new fabric.Canvas('canvas')
        }
    }
</script>

<style scoped>
.drawing-area{
    position: absolute;
    top: 60px;
    left: 122px;
    z-index: 10;
    width: 200px;
    height: 400px;
}

.canvas-container{
    width: 200px;
    height: 400px;
    position: relative;
    user-select: none;
}

#tshirt-div{
    width: 452px;
    height: 548px;
    position: relative;
    background-color: #fff;
}

#canvas{
    position: absolute;
    width: 200px;
    height: 400px;
    left: 0px;
    top: 0px;
    user-select: none;
    cursor: default;
}
</style>
