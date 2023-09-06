<template>
  <div id="cesiumContainer"></div>
</template>
<script setup>
import * as Cesium from "cesium";
import { onMounted } from "vue";

//cesium初始化必须写在mounted生命周期里面，否则会报错"Element with id "cesiumContainer" does not exist in the document."
onMounted(() => {
  const viewer = new Cesium.Viewer('cesiumContainer', {
    infoBox: false, // 是否顯示訊息框 禁用，解决控制台报错
    // animation: true, // 是否開啟動畫儀錶板
    // timeline: true, // 是否顯示底部時間軸
    // baseLayerPicker: false, //右上角的圖層選擇按鈕
    // geocoder: false, //搜索框
    // homeButton: false, //home按钮
    // sceneModePicker: false, // 2D,3D Columbus View 模式切換按鈕
    // navigationHelpButton: false, //右上角的幫助按鈕
    // fullscreenButton: false, //右下角的全屏按鈕
    // selectionIndicator: false, //是否顯示選取指示器組件
    // zoomIndicatorContainer: false,
    // navigation: false, //指南针
    // scene3DOnly:true //只渲染3D 節省CPU
      // shadows: true, //陰影
  });
  // 去除版權訊息
   viewer._cesiumWidget._creditContainer.style.display = "none";
  //   console.log("Cesium.VERSION", Cesium.VERSION);
  //   Cesium.Ion.defaultAccessToken =
  //     "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJqdGkiOiIxNTFlNWVmMC1jOWRhLTQyMDktOTU5YWFlMGYwY2IiLCJpZCI6OTQzNDQsImlhdCI6MTY1Mjg4ODEyNn0.g2vq1qq_rdfZeRTy73nBkEDzhMIM4upkYcbIdFYnCiQ";

  //   var viewer = new Cesium.Viewer("cesiumContainer", {
  //     // animation: true, // 是否開啟動畫
  //     // timeline: true, // 是否顯示時間軸
  //   });
  //   viewer.scene.globe.show = true;

  //   // This works
  //   viewer.infoBox.frame.removeAttribute("sandbox"); // 必须要加，不然會報錯： Can’t run scripts in infobox

  //   // So does this if you want to limit other things but allow scripts
  //   //viewer.infoBox.frame.setAttribute("sandbox", "allow-same-origin allow-popups allow-forms allow-scripts");

  //   // In both cases, you need to do this to force a reload for the change to take affect.
  //   viewer.infoBox.frame.src = "about:blank";

  //   viewer.selectedEntity = new Cesium.Entity({
  //     id: "YouTube video",
  //     description:
  //       '<div style="height:315px;"><iframe width=100% height="315" src="https://www.youtube.com/embed/wo5rWeeZxvo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div>',
  //   });
});
</script>

