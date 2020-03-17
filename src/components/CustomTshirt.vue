<template>
    <div class="main">
        <div class="title mx-auto">
            <h1>Create your custom t-shirt! 👕 </h1>
        </div>
        <div class="container">
            <div id="tshirt-canvas" :style="{background: selectColor}">
                <img id="tshirt-bg" src="../assets/img/bg-tshirt.png"/>
                <div id="drawingArea" class="drawing-area">
                    <div class="canvas-container">
                        <canvas id="canvas" ></canvas>
                    </div>
                </div>
            </div>
            <div class="setting">
                <v-card style="width: 100%; height: 100%;">
                    <v-tabs  v-model="tab"
                             color="#7E57C2"
                             light
                             grow
                    >
                      <v-tab v-for="(item, index) in items" :key="index" >
                        {{ item.name }}
                      </v-tab>
                    </v-tabs>
                    <v-tabs-items v-model="tab">
                      <v-tab-item
                        v-for="(item, index) in items" :key="index"
                      >
                          <template v-if="item.name === COLOR">
                              <choose-color @selectedColor="selectColor = $event"
                              ></choose-color>
                          </template>
                          <template v-else-if="item.name === IMAGE">
                              <choose-image></choose-image>
                          </template>
                          <template v-else>
                              <add-text></add-text>
                          </template>
                      </v-tab-item>
                    </v-tabs-items>


                </v-card>
            </div>
        </div>
    </div>

</template>

<script>
    import { fabric } from 'fabric'
    import AddText from './AddText'
    import ChooseColor from './ChooseColor'
    import ChooseImage from './ChooseImage'
    export default {
        name: "CustomTshirt",
        components: {AddText, ChooseImage, ChooseColor},
        data() {
            return {
                canvas: null,
                COLOR: 'color',
                IMAGE: 'image',
                TEXT: 'text',
                tab:null,
                items: [
                    { name : 'color' },
                    { name: 'image' },
                    { name: 'text' }
                ],
                selectColor: ''
            }
        },
        component: [
            AddText,
            ChooseImage,
            ChooseColor
        ],
        beforeMount() {
             this.canvas = new fabric.Canvas('canvas')
        },
        methods: {
        }
    }
</script>

<style scoped>
    .main {
        width: 100%;
        height: 100%;
        align-items: center;
    }
    .title {
        display: flex;
        width: 100%;
        height: 100px;
        background: linear-gradient(to right, #7E57C2, #5C6BC0, #42A5F5);
        font-family: 'Lato';
        align-items: center;
    }
    .container {
        display: flex;
        width: 100%;
    }
    #tshirt-canvas {
        width: 50%;
        height: 600px;
        position: relative;
        background-color: #fff;
        margin: 20px;
    }
    #tshirt-bg {
        width: 100%;
        height: 100%;
    }

    .drawing-area {
        position: absolute;
        top: 80px;
        left: 130px;
        z-index: 10;
        width: 300px;
        height: 600px;
    }
    .canvas-container {
        width: 280px;
        height: 460px;
        position: relative;
        user-select: none;
    }

    #canvas {
        position: absolute;
        width: 280px;
        height: 460px;
        left: 0px;
        top: 0px;
        user-select: none;
        cursor: default;
    }
    .setting {
        width: 50%;
        height: 600px;
        position: relative;
        margin: 20px;
    }
</style>
