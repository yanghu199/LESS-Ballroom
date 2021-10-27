week7

Less festival pitch

In this week we had a more specific and detailed plan for our contribution to less festival individually. After did some visual references of the virtual exhibition, I started to design the whole structure for mine. The initially idea was a endless tower contained various style windows, audience could see different artworks through those windows. The style of those windows could be ancient (traditional Chinese style, Medieval, Hellenism, Rococo style, Ancient Egypt...); or modern ( Minimalism, Pop Art, Fauvism, Cubism, Surrealism, Abstractionism, Futuristic, Cyberpunk...) I started with some simple windows as a prototype to test the color palette and the basic interior design of the tower. Besides, if I wanted to achieve the endless spiral stairs, 

<img width="1680" alt="截屏2021-09-08 下午11 38 55" src="https://user-images.githubusercontent.com/68723373/139079093-500b412c-dc5e-43b6-a2b9-5aeedca90745.png">
<img width="1680" alt="截屏2021-09-08 下午11 56 03" src="https://user-images.githubusercontent.com/68723373/139079104-001dec9f-b4cd-4496-b793-961c9bd9bb1d.png">


Band tour - merchandises

<img width="1007" alt="截屏2021-10-27 下午9 51 21" src="https://user-images.githubusercontent.com/68723373/139079496-bc8a8d5e-86c2-4a08-bb8e-d4b51043e7d1.png">
<img width="893" alt="截屏2021-10-27 下午9 51 47" src="https://user-images.githubusercontent.com/68723373/139079506-adf05653-bbf8-42fb-a792-29985b280c61.png">
<img width="1201" alt="截屏2021-10-27 下午9 52 06" src="https://user-images.githubusercontent.com/68723373/139079517-901088f8-4c83-4a03-a3db-eeeadbc09438.png">

P5js portrait

<img width="1556" alt="截屏2021-09-09 下午2 02 07" src="https://user-images.githubusercontent.com/68723373/139078946-c61e7853-f756-41e5-9f7b-48f57b24c147.png">

let ball;
let skin;


function preload (){
ball = loadModel ('data/ball.obj',true);
skin = loadImage ('data/skin.jpg',true);


}

function setup() {
 createCanvas(windowWidth, windowHeight,WEBGL);
 
}


function draw() {
 background(0,17,255);
   scale(5);
  rotate(PI / 1.0);
 // rotateX(frameCount * 0.02);
  //rotateY(frameCount * 0.03);
 noStroke();
//translate(mouseX-width/2,mouseY-height/2);
//translate(160,90,260);

  texture(skin);
 model(ball);
 
 fill(255,0,0);
 noStroke();
 ellipse(mouseX,mouseY,100,100);


}

Text based works

Image collection digital version

