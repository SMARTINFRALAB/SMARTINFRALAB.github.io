---
permalink: /
title: "About"
excerpt: ""
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

{% include base_path %}

Our goal is to build the <i>smart and connected</i> water systems of the future.

<div id="webgl"></div>
<script src="../lib/three.min.js"></script>
<script src="../lib/TerrainLoader.js"></script>
<script>

 "use strict";

 var scene = new THREE.Scene();
 scene.background = new THREE.Color( 0x1a202c );

 var axes = new THREE.AxesHelper(0);
 scene.add(axes);

 const ambientLight = new THREE.AmbientLight(0xffffff, 0.9);

 scene.add(ambientLight);

 var renderer = new THREE.WebGLRenderer();
 document.body.appendChild(renderer.domElement);

 var camera = new THREE.PerspectiveCamera(45, 1, 0.1, 1000);
 camera.position.set(0, -50, 50);
 camera.rotation.set(3.14 / 4, 0, 0);

 function resizeCanvasToDisplaySize() {
    const canvas = renderer.domElement;
    const width = canvas.clientWidth;
    const height = canvas.clientHeight;
    if (canvas.width !== width ||canvas.height !== height) {
        renderer.setSize(width, height, false);
        camera.aspect = width / height;
        camera.updateProjectionMatrix();
    }
 }

 var terrainLoader_0 = new THREE.TerrainLoader();
 var terrainLoader_1 = new THREE.TerrainLoader();
 terrainLoader_0.load('../files/jotunheimen_flood.bin', function(data) {

     terrainLoader_1.load('../files/jotunheimen.bin', function(data) {
         const width = 200;
         const height = 200;
         const size = width * height;
         var geometry = new THREE.PlaneGeometry(45, 45, width - 1, height - 1);
         var texture_data = new Uint8ClampedArray(size);

         for (var i = 0, l = geometry.attributes.position.count; i < l; i++) {
             geometry.attributes.position.setZ(i, data[i] / 65535 * 10);
         }

         for (var i = 0, l = size; i < l; i++) {
             texture_data[i] = (data[i] / 65535 * 255);
         }

         const texture = new THREE.DataTexture(texture_data, width, height,
                                               THREE.LuminanceFormat, THREE.UnsignedByteType,
                                               THREE.UVMapping,
                                               THREE.ClampToEdgeMapping, THREE.ClampToEdgeMapping);
         texture.flipY = true;

         var material = new THREE.MeshBasicMaterial({
             map: texture,
             wireframe: false
         });

         var plane = new THREE.Mesh(geometry, material);
         scene.add(plane);
     });

     const width = 200;
     const height = 200;
     const size = width * height;
     var geometry = new THREE.PlaneGeometry(45, 45, width - 1, height - 1);
     var texture_data = new Uint8ClampedArray(size);

     for (var i = 0, l = geometry.attributes.position.count; i < l; i++) {
         geometry.attributes.position.setZ(i, (data[i] - 200) / 65535 * 10);
     }

     var material = new THREE.MeshBasicMaterial({
         color: 0x00ffff,
         opacity: 0.4,
         transparent: true,
         wireframe: false
     });

     var plane = new THREE.Mesh(geometry, material);
     scene.add(plane);

 });

 document.getElementById('webgl').appendChild(renderer.domElement);

 function animate() {

     resizeCanvasToDisplaySize();

     if (scene.children.length > 3) {
         scene.children[2].rotation.z += 0.005;
         scene.children[3].rotation.z += 0.005;
     }
     requestAnimationFrame(animate);
     renderer.render(scene, camera);
 }

 animate();

</script>

<!-- <div class="page__col-wrap"></div> -->

<h1>News</h1>

<details open>
    <summary><u>Recent</u></summary>
     <ul>
        <li>[2022-01-10] : Matt and Jeil present at UDM.</li>
        <li>[2021-12-14] : Matt presents at AGU.</li>
        <li>[2021-10-22] : Matt presents at the WCE Seminar Series.</li>
        <li>[2021-10-01] : «Pipedream» published in EMS.</li>
     </ul>
</details>

<details>
    <summary><u>Older</u></summary>
     <ul>
        <li>[2021-07-21] : Matt interviewed in El Paso Matters.</li>
        <li>[2021-06-26] : «Observability-based sensor placement» published in WRR.</li>
        <li>[2021-05-13] : Matt presents at INCOSE.</li>
        <li>[2021-02-09] : «Multipollutant monitors» published in AMT.</li>
        <li>[2021-01-21] : Matt presents at EWRE Seminar Series.</li>
    </ul>
</details>

<!-- <div class="page__col-wrap"></div> -->

<!-- <h1>Research</h1> -->

<!-- We investigate how real-time sensing and control can solve modern water challenges. -->

<!-- <div class="page__col-wrap"> -->
<!-- <div class="page__lcol"><img src="/images/sensors_mini.png"></div> -->
<!-- <div class="page__rcol"><h2><a href="/research/wireless-sensor-networks">Wireless sensor networks for water infrastructure</a></h2> New technologies are enabling real-time supervision and control of previously static stormwater and flood control infrastructure. We are designing a new generation of cyber-physical systems that incorporate low-power embedded electronics, wireless communications, and web services to transform passive water systems into active ones. -->
<!-- </div> -->
<!-- </div> -->

<!-- <div class="page__col-wrap"> -->
<!-- <div class="page__lcol"><img src="/images/state_estimation.png"></div> -->
<!-- <div class="page__rcol"><h2><a href="/research/estimation-and-control">State estimation and control</a></h2> Like self-driving cars, autonomous water systems will require new algorithms to estimate system dynamics from sensor data and guide system behavior towards desirable states. We are exploring how advances in modern control theory can improve our understanding of water infrastructure and inform better operational resilience. -->
<!-- </div> -->
<!-- </div> -->

<!-- <div class="page__col-wrap"> -->
<!-- <div class="page__lcol"><img src="/images/digital_twins.png"></div> -->
<!-- <div class="page__rcol"><h2><a href="/research/digital-twins">Digital twin models of water infrastructure</a></h2> Water managers are increasingly seeking <i>digital twins</i> of real-world water networks that combine sensor data with online models in order to better understand and control system dynamics. In service of this goal, we are building new real-time models that will allow operators to geolocate flooding, detect maintenance emergencies, and better implement dynamic control. -->
<!-- </div> -->
<!-- </div> -->

<!-- <div class="page__col-wrap"> -->
<!-- <div class="page__lcol"><img src="/images/powerlines.png"></div> -->
<!-- <div class="page__rcol"><h2><a href="/research/coupled-infrastructure-modeling">Coupled infrastructure system modeling</a></h2> Water, energy, and transportation grids are closely linked; yet their coupled dynamics are still poorly understood. We are exploring how critical infrastructure systems interact in a dynamical context, and how coordinated sensing, modeling and control can achieve better resilience of civil systems as a whole. -->
<!-- </div> -->
<!-- </div> -->
