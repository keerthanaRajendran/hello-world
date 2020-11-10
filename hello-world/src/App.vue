<template>
  <div class="md-layout">
         <div class="control-section" style="width: 100%; max-width:995px; height:auto; margin-left:auto; margin-right:auto; z-index:1;margin-bottom:25px; margin-top:25px;">
                     <ejs-dashboardlayout id="defaultLayout"
                                          :columns=12
                                          v-bind:showGridLines="true"
                                          v-bind:allowResizing="true"
                                          v-bind:allowDragging="true"
                                          :draggableHandle="'.e-panel-header'"
                                          :cellAspectRatio="100/100"
                                          :allowFloating="true"
                                          style="background-color: rgba(255,255,255,0);">
                         <div   v-for="(item, index) in items"
                              v-bind:key="index"
                              v-bind:id="item.id.substring(0,8)"
                              class="e-panel"
                              v-bind:data-row="item.row"
                              v-bind:data-col="item.col"
                              v-bind:data-sizeX="item.sizeX"
                              v-bind:data-sizeY="item.sizeY"
                              style="z-index:1;"
                             >
                                 <!-- Drag Handler -->
                             <div class="e-panel-header" style="height:10px;text-align: center;color:#888;line-height:15px; position:absolute; z-index:2;" >
                                 <div>&#8226;&#8226;&#8226;</div>
                             </div>
                                 <!-- Components -->
                                 <div class="e-panel-content">
                                    <div>value</div>
                                 </div>
                        </div>
                    </ejs-dashboardlayout>
                </div>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () {
    return {
         items: [
        {
          sizeX: 1,
          sizeY: 1,
          row: 0,
          col: 0,
          id: "s584"
        },
         {
          sizeX: 1,
          sizeY: 1,
          row: 0,
          col: 1,
          id: "s684"
        },
       
      ]
    }
  },
provide: {
    
  },
  methods: {
        
 }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
@import "../node_modules/@syncfusion/ej2-base/styles/material.css";
@import "../node_modules/@syncfusion/ej2-vue-layouts/styles/material.css";
 #defaultLayout, .e-panel, .e-panel-container {
        vertical-align: middle;
        text-shadow: none;
        border: none;
    }
    .text-align {
        line-height: 80px;
    }
    .pageCover {
        width: 100%;
        transition: height 350ms ease-in-out;
        overflow: auto;
    }
    .configCardPanel {
        transition: height 500ms ease-in-out;
    }
    .pageConfigPanel {
        overflow:hidden;
        transition:max-height 750ms ease-in-out;
        height:auto;
        max-height:800px;
    }
    .pageConfigPanel.collapsed {
        max-height:0;
    }
    .icon-scroll,
    .icon-scroll:before{
        position: absolute;
        left: 50%;
    }
    .icon-scroll{
        width: 40px;
        height: 70px;
        margin-left: -20px;
        bottom: 4%;
        margin-top: -35px;
        box-shadow: inset 0 0 0 1px #fff;
        border-radius: 25px;
    }

    .icon-scroll:before{
        content: '';
        width: 8px;
        height: 8px;
        background: #fff;
        margin-left: -4px;
        top: 8px;
        border-radius: 4px;
        animation-duration: 1.5s;
        animation-iteration-count: infinite;
        animation-name: scroll;
    }

    @keyframes scroll {
        0% { opacity: 1 }
        100% { opacity: 0; transform: translateY(46px)}
    }
    .fade-enter-active, .fade-leave-active {
        transition: opacity 1s;
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
        opacity: 0;
    }

</style>
