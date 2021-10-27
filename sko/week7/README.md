week7

Less festival pitch

In this week we had a more specific and detailed plan for our contribution to less festival individually. After did some visual references of the virtual exhibition, I started to design the whole structure for mine. The initially idea was a endless tower contained various style windows, audience could see different artworks through those windows. The style of those windows could be ancient (traditional Chinese style, Medieval, Hellenism, Rococo style, Ancient Egypt...); or modern ( Minimalism, Pop Art, Fauvism, Cubism, Surrealism, Abstractionism, Futuristic, Cyberpunk...) I started with some simple windows as a prototype to test the color palette and the basic interior design of the tower. Besides, for achieving the endless spiral stairs, I found someone built a similar function in github => https://github.com/fritx/threejs-galaxy (he created a galaxy with endless planets and they can crash with each other!)

<img width="1680" alt="截屏2021-09-08 下午11 38 55" src="https://user-images.githubusercontent.com/68723373/139079093-500b412c-dc5e-43b6-a2b9-5aeedca90745.png">
<img width="1680" alt="截屏2021-09-08 下午11 56 03" src="https://user-images.githubusercontent.com/68723373/139079104-001dec9f-b4cd-4496-b793-961c9bd9bb1d.png">

The inspirations came from :

1. Giorgio de Chirico - con monumento ad un uomo politico

One Italian critic of the early 20th century, Ardengo Soffici, wrote in 1914, “The painting of de Chirico is not painting, in the sense that we use that word today. It could be defined as a writing down of dreams. … He truly succeeds in expressing that sensation of vastness, of solitude, of immobility, of stasis which certain sights reflected by the state of memory sometimes produce in our mind, just at the point of sleep.”

These strange juxtapositions are foreboding—and today perhaps even prescient of numerous cities under lockdown. Christov-Bakargiev said, “When we walk in Turin today, it is as if we are walking inside a de Chirico. What is a city without people, what is the point of an empty piazza?”

![2f78f0622b6611c750ce2f01a61d4e95](https://user-images.githubusercontent.com/68723373/139103852-69be819f-2b87-4190-b044-250bb6454af9.jpg)
![f341c818694295a697c0b79666cfd047](https://user-images.githubusercontent.com/68723373/139103858-8fe43ccb-8f06-488d-a64e-52fb8a62272b.jpg)

The fascination with dreams, mystery and fear are the hidden themes at the turn of the century, and Chirico accurately presented them. He once said: The structure of the city, such as houses, squares, gardens, railway stations and other structures, has brought us a huge and most essential physical (metaphysical) beauty. We live in metaphysical symbols, and deeply understand the joys and sorrows carried on them.

I found that he had an unprecedented performance of secrecy. Those thick shadows and empty buildings invisibly construct a kind of eternity, which annihilates all sensible emotions, standing in the center of the square, as if standing in a spiritual ruin from which life has been extracted, beyond words. He used the architecture as the container to deliever the message to audience, which inspired me to create a kind of 'architecture collage' in virtual world.

2. Hu JieMing - view finder

![8b71573c513033a41f045e411aa2f33a](https://user-images.githubusercontent.com/68723373/139105481-f1679341-e115-4f91-93ea-60c4af9ddc07.jpg)
![893a3113eb39cc2769b72ba63fcbfbdc](https://user-images.githubusercontent.com/68723373/139105493-e9d6dfc8-f163-4df1-91c8-b8248b4c03c1.jpg)
![a0a13d7282a3043cf56236853f81d1b4](https://user-images.githubusercontent.com/68723373/139105498-65c0da50-d5ea-45af-98b2-a558ab136a6a.jpg)

During the three days of on-site creation, through the camera’s viewing frame, the artist captured images in the “glass window” and was strongly attracted by the skylight: “The huge glass dome looks like an iconic container for fashion consumption. It conveys internal and external information. There is no doubt that this place can be regarded as the origin of the "glass window", colored... I feel that the possibility of reorganizing these elements exists, and is even effective." These localities The elements of to help creators focus and think in the material, complex, colorful and noisy shopping mall space, and transform it into visual symbols in meditation.

As the symbol of communicate with another environment/medium/world/universe, windows can create a feeling of 'traversing' and remind people that there is a different world outside, which was also the message I wanted to express to the audience that they were entering a collage world.

Band tour - merchandises

<img width="1007" alt="截屏2021-10-27 下午9 51 21" src="https://user-images.githubusercontent.com/68723373/139079496-bc8a8d5e-86c2-4a08-bb8e-d4b51043e7d1.png">
<img width="893" alt="截屏2021-10-27 下午9 51 47" src="https://user-images.githubusercontent.com/68723373/139079506-adf05653-bbf8-42fb-a792-29985b280c61.png">
<img width="1201" alt="截屏2021-10-27 下午9 52 06" src="https://user-images.githubusercontent.com/68723373/139079517-901088f8-4c83-4a03-a3db-eeeadbc09438.png">

We continually created our hypothetical band and I selected the high-heeled shoes and high boots with teeth as decoration. Meanwhile, I built a virtual Vocals as the advertisement star (without gender feature) in our promotional poster.

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

