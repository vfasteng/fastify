<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Inspector Test - Embedded (Bad)</title>
    <script src="https://cdn.jsdelivr.net/gh/aframevr/aframe/dist/aframe-master.min.js"></script>
    <style>
      html,
      body {
        background: #111;
        height: 100%;
        width: 100%;
      }
      body {
        align-items: center;
        display: flex;
        justify-content: center;
      }
    </style>
  </head>
  <body>
    <div style="bottom: 0; left: 0; margin: 0 auto; right: 0; position: absolute; top: 0; width: 960px; zoom: 1.1">
      <div style="height: 480px; width: 640px">
        <a-scene embedded inspector="url: ../dist/aframe-inspector.js">
          <a-assets>
            <a-mixin id="blue" material="color: #4CC3D9"></a-mixin>
            <a-mixin id="blueBox" geometry="primitive: box; depth: 2; height: 5; width: 1" material="color: #4CC3D9"></a-mixin>
            <a-mixin id="box" geometry="primitive: box; depth: 1; height: 1; width: 1"></a-mixin>
            <a-mixin id="cylinder" geometry="primitive: cylinder; height: 0.3; radius: 0.75; segmentsRadial: 6"></a-mixin>
            <a-mixin id="green" material="color: #7BC8A4"></a-mixin>
            <a-mixin id="orange" material="color: #F16745"></a-mixin>
            <a-mixin id="purple" material="color: #93648D"></a-mixin>
            <a-mixin id="short" scale="1 0.5 1"></a-mixin>
            <a-mixin id="yellow" material="color: #FFC65D"></a-mixin>
            <img id="crateImg" src="assets/textures/crate.gif">
            <img id="floorImg" src="assets/textures/grasslight-big.jpg">
          </a-assets>

          <!-- Meshes. -->
          <a-entity id="blueBox" mixin="blueBox" position="0 8 0"></a-entity>
          <a-entity id="shortOrangeBox" mixin="short orange box" position="-5 2 0"></a-entity>
          <a-entity id="shortYellowBox" mixin="short yellow box" position="5 2 0"></a-entity>
          <a-entity id="redBox" geometry="primitive: box" material="color:#f00" position="-4 1 0">
            <a-animation attribute="rotation" to="0 360 0" repeat="indefinite" easing="linear" dur="9600"></a-animation>
          </a-entity>
          <a-entity id="yellowSphere" geometry="primitive: sphere" material="color:#ff0; metalness:0.0; roughness:1.0" position="-2 2 -2"></a-entity>
          <a-box src="assets/textures/brick_bump.jpg" position="-5 5 -2" width="1" color="#F16745"></a-box>
          <a-box id="box" position="0 2 0" height="2" color="#FFC65D"></a-box>

          <!-- Models. -->
          <a-entity id="crate" geometry="primitive: box" material="src: #crateImg" position="3 4 0"></a-entity>
          <a-entity id="greenBox" geometry="primitive: box" material="color: #0f0" position="4 2 4"></a-entity>

          <!-- Floor. -->
          <a-entity id="floor" geometry="primitive: cylinder; height: .2; radius: 12"
                    material="src: #floorImg; color: #fafafa; metalness: .2; repeat: 50 20; roughness: .1"></a-entity>

          <!-- Lights. -->
          <a-entity id="pointLight" light="type: point" position="0 3 3"></a-entity>

          <!-- Camera. -->
          <a-entity id="cameraWrapper" position="0 1 8">
            <a-entity id="camera" camera look-controls wasd-controls>
              <!-- Cursor. -->
              <a-entity id="cursor" position="0 0 -2"
                        geometry="primitive: ring; radiusOuter: 0.016; radiusInner: 0.01"
                        material="color: #ff9; shader: flat; transparent: true; opacity: 0.5"
                        scale="2 2 2" raycaster>
              </a-entity>
            </a-entity>
          </a-entity>

          <a-sky color="#333"></a-sky>
        </a-scene>
      </div>
    </div>
  </body>
</html>

