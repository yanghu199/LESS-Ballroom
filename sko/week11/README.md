week11

Coding research

After week 10 we had discussion on the specific functions of the dressup game, I started to look for the similar coding in github that I could adjust.

sample in three.js web that can change the color and type of the cars: https://carvisualizer.plus360degrees.com/threejs/

code: 
https://github.com/heavis/threejs-demo/tree/762fc67830a21fffcdbbb0d041441d8c1fe5ee44
https://github.com/corefan/something/tree/b923e57841f2c236de2b440467cd23c345e6d32d/Three
https://github.com/boyaquito/three.js

code I used:
https://blog.csdn.net/biyusr/article/details/116267042?ops_request_misc=&request_id=&biz_id=102&utm_term=threejs切换模型&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-3-116267042.nonecase&spm=1018.2226.3001.4187
https://download.csdn.net/download/yanlovesky/10188356?utm_medium=distribute.pc_relevant.none-task-download-2%7Edefault%7ECTRLIST%7Edefault-15.no_search_link&depth_1-utm_source=distribute.pc_relevant.none-task-download-2%7Edefault%7ECTRLIST%7Edefault-15.no_search_link

<body>
	<div>
		<img class='clicked person' src="fbx/image/person.png" id="personId">

		<div id="allId">
			<a href="play.html" target="blank">
				<img class='clicked done' src="fbx/image/done.png">
			</a>

			<img class='clicked home' src="fbx/image/home.png" id="homeId">

			<img class='tex-bg' src="fbx/image/tex-bg.png">
			<img class='clicked collage-1' src="fbx/image/collage1.png" id="texture1">
			<img class='clicked collage-2' src="fbx/image/collage2.png" id="texture2">
			<img class='clicked collage-3' src="fbx/image/collage3.png" id="texture3">
			<img class='clicked collage-4' src="fbx/image/collage4.png" id="texture4">
			<img class='clicked collage-5' src="fbx/image/collage5.png" id="texture5">
			<img class='clicked collage-6' src="fbx/image/collage6.png" id="texture6">
			<img class='clicked collage-7' src="fbx/image/collage7.png" id="texture7">
			<img class='clicked collage-8' src="fbx/image/collage8.png" id="texture8">

			<img class='dress-bg' src="fbx/image/dress-bg.png">
			<img class='clicked dress-1' src="fbx/image/dress1.png" id='dress1'>
			<img class='clicked dress-2' src="fbx/image/dress2.png" id='dress2'>
			<img class='clicked dress-3' src="fbx/image/dress3.png" id='dress3'>
			<img class='clicked dress-4' src="fbx/image/dress4.png" id='dress4'>
			<img class='clicked dress-5' src="fbx/image/dress5.png" id='dress5'>
			<img class='clicked dress-6' src="fbx/image/dress6.png" id='dress6'>
			<img class='clicked dress-7' src="fbx/image/dress7.png" id='dress7'>
		</div>

	</div>

	<script type="module">

		import * as THREE from './build/three.module.js';
		import { TrackballControls } from './jsm/controls/TrackballControls.js';
		import { FBXLoader } from './jsm/loader/FBXLoader.js';

		var container, stats, controls;
		var camera, scene, renderer, light;

		var clock = new THREE.Clock();

		var mixer;

		var fbxLoader = new FBXLoader();
		var textureLoader = new THREE.TextureLoader()

		var inner1 = new THREE.Vector3(3.6, 71, 74), inner2 = new THREE.Vector3(5, 24.5, 1.2)
		var outer1 = new THREE.Vector3(20, 196, 516), outer2 = new THREE.Vector3(5, 24.5, 1.2)

		init();
		animate();

		function init() {

			container = document.createElement('div');
			document.body.appendChild(container);

			camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 0.01, 10000);
			window.camera = camera
			// camera.up.set(0, 1, 0)
			camera.position.copy(outer1)

			scene = new THREE.Scene();
			scene.background = new THREE.Color(0x000000);
			// scene.add(new THREE.AmbientLight(0xff0000));


			/* var grid = new THREE.GridHelper(2000, 20, 0x000000, 0x000000);
			grid.material.opacity = 0.2;
			grid.material.transparent = true;
			scene.add(grid); */

			renderer = new THREE.WebGLRenderer({ antialias: true });
			renderer.setPixelRatio(window.devicePixelRatio);
			renderer.setSize(window.innerWidth, window.innerHeight);
			renderer.shadowMap.enabled = true;
			container.appendChild(renderer.domElement);

			controls = new TrackballControls(camera, renderer.domElement)
			controls.rotateSpeed = 1.0
			controls.zoomSpeed = 0.5
			controls.panSpeed = 0.5
			controls.target.copy(outer2)

			loadBgModel()

			window.addEventListener('resize', onWindowResize, false);
			for (let i = 1; i <= 7; i++) {
				document.getElementById('dress' + i).addEventListener("click", changeDress)
			}
			for (let i = 1; i <= 8; i++) {
				document.getElementById('texture' + i).addEventListener("click", changeImage)
			}

			document.getElementById('homeId').addEventListener("click", function () {
				document.getElementById('personId').style.display = 'block'
				document.getElementById('allId').style.display = 'none'

				camera.position.copy(outer1)
				controls.target.copy(outer2)
			})

			document.getElementById('personId').addEventListener("click", function () {
				this.style.display = 'none'
				document.getElementById('allId').style.display = 'block'

		
			})


			window.scene = scene
			window.control = controls
		}

		function loadModel(modelId, clothId) {

		}
		function loadBgModel() {
			fbxLoader.load('fbx/ballroom-new-web.fbx', function (object) {

				scene.add(object);
			});
		}

		function changeImage() {
			let id = this.id
			scene.traverse(function (child) {
				if (child.name == 'dress') {
					child.children[0].material.map = textureLoader.load('fbx/dress/' + id + '.jpg')
					
				}
			});
		}

		function changeDress() {
			scene.traverse(function (child) {
				if (child.name == 'dress') scene.remove(child)
			})

			fbxLoader.load('fbx/dress/' + this.id + '.fbx', function (object) {
				object.name = 'dress'
				scene.add(object);
			});
		}

		function onWindowResize() {

			camera.aspect = window.innerWidth / window.innerHeight;
			camera.updateProjectionMatrix();

			renderer.setSize(window.innerWidth, window.innerHeight);

		}

		//

		function animate() {

			requestAnimationFrame(animate);

			var delta = clock.getDelta();

			if (mixer) mixer.update(delta);

			renderer.render(scene, camera);
			controls.update()

		}

	</script>

</body>

<img width="1555" alt="截屏2021-11-02 下午3 50 37" src="https://user-images.githubusercontent.com/68723373/139806610-e4226032-02d3-4f06-8fe3-1643d1ecd2a6.png">

The problem of this code test 03 was the perspective of the camera when clicked the button'dress me', which should be automatically changed to the camera 2:faced the model. Also the texture changing was not working.

 document.getElementById('personId').addEventListener("click", function () {
				this.style.display = 'none'
				document.getElementById('allId').style.display = 'block'

				camera.position.copy(inner1)
				controls.target.copy(inner2)
			})
      
 Added the inner camera could fix that.
 
 The texture changing had some logical issues, needed to be identified 'dress' as child.name
 
 function changeImage() {
			let id = this.id
			scene.traverse(function (child) {
				if (child.name == 'dress') {
					child.children[0].material.map = textureLoader.load('fbx/dress/' + id + '.jpg')
					child.children[0].material.needsUpdate = true
				}
			});
		}

Adjust lighting and broken models. The process of uploading the scenario model was not worked as successfully as I thought, even I had the experience from last year. In this time, the problem was not the disappear of the model, but the problem of lighting and some missing parts of the model(walls, some polygons in the clothes models...). After researched I realized that was the problem of triangle mesh and quadrilateral mesh. The dresses models that provided from designers are triangle mesh, and the scenariio I built in c4d was quadrilateral mesh, maybe that confused threejs? (I was not really sure it was because of this reason) So I transfered all model into triangle mesh and it finally appeared in web view! The second issuess was the broken part of the wall of the ballroom. Initially I combined all components of the building together but it still vanished in web. Why only the wall disappeared but other parts still exist although they were not separated? Then I tested different versions of the buildings and found that it’s becuase the wall was composed by planes without thickness. 

<img width="1148" alt="截屏2021-10-23 上午1 06 54" src="https://user-images.githubusercontent.com/68723373/139808284-8851ef5b-a179-4e2f-bfe2-5d5f6d41cf1b.png">

