# class trial 

```
function setup(){
createCanvas(400,400);
}
```

we are giving command to keep everything in its place in the program. we are creating the canvas by giving x and y position.

```
function draw(){
rect(380,mouseY,10,100);
}
```

giving a command to draw a rectangle which is controlled by the mouse so that it can be moved along the Y axis.

# class 1

```
var playerPaddle;

function setup(){
  createCanvas(400,400);
  //player Paddle
  playerPaddle = new Paddle();
}

```

creating a memory for the player paddle.

creating a  paddle for the player.

creating a canvas of 400,400 size.

```
function draw() {
  //set background to white
  background("white");
  
  
  playerPaddle.xPosition = 390;
  playerPaddle.yPosition = mouseY;
  
  playerPaddle.display();
  
  //computer paddle
  var computerPaddle = new Paddle();
  computerPaddle.xPosition = 0;
  computerPaddle.yPosition = 150;
  
  computerPaddle.display();
  
  //draw the ball
  rect(200,200,10,10);
}
```

creating a background to hide the loops.

giving player X position and telling it to follow the mouse on the y axis.

giving display command to see the objects on screen. 

creating a new paddle for the computer.



# class 2

```
var ball = createSprite(200,200,10,10);
ball.shapeColor="purple";
ball.velocityX = -2;
ball.velocityY = -3;
```

making a ball and giving it colour

adding velocity to the ball

```
 ball.bounceOff(edges);
  ball1.bounceOff(edges);
  ball2.bounceOff(edges);
  ball3.bounceOff(edges);
  ball4.bounceOff(edges);
  ball5.bounceOff(edges);
```

making all the balls bounce off the edges

```
ball.bounce(ball1);
ball.bounce(ball2);
```

making the ball bounce  ball1 when they touch

note- give the bounce command in order

# class 3

```
if (keyDown("DOWN_ARROW")) {
  ball.velocityY= 2;
  ball.velocityX=0;
```

if a down arrow is pressed the ball will start moving.

```
if (ball.isTouching(wall)) {
 ball.x=200;
 ball.y=200;
}
```

if the ball touches the wall it should go back in the center

# class 4

```
playerpaddle.y=World.mouseY;
```

telling the player paddle to follow the mouse

```
computerpaddle.y=ball.y;
```

telling the computer paddle to follow the ball

```
if (keyDown("space")) {
//giving x and y velocity to ball
ball.velocityY=3;
ball.velocityX=3;
}
```

using space key to move the ball

# Class 5

1) 

```
function drawnet() {
for (var i = 0; i < 400; i=i+20) 
line(200,i,200,i+10);
}
```

This creates a different a function for a line to be drawn in the middle. It means that it creates a line on the y-axis and after every line it adds another one to give a repeated effect.



2) 

```
function serveball() {
ball.velocityX=5;
ball.velocityY=0;
}
```

This is one of the states of the game called serveball. This is just so we can keep serving the ball whenever we press the space key.



3) 

```
function resetball() {
ball.x=200;
ball.y=200;
ball.velocityX=0;
ball.velocityY=0;
}
```

We are using this function because it helps us to keep serving the ball through out the game and return to its original position.



# Class 6

1) 

```
if (gameState === "serve") {
  text("Press Space to Serve",150,180);
  text(computerScore,170,11);
  text(playerScore,227,11);

}
```

This means that whenever the gameState of the game is serve then a text should be displayed, as well as the computer and player score.



2)

```
 if(ball.x > 400 || ball.x <0) {
    if(ball.x > 400){
    computerScore = computerScore+1;
    }
    if(ball.x<0){
    playerScore = playerScore+1;
    }
    
   reset();
    gameState="serve";
    }


```

Whenever, someone wins, automatically one point gets added on it's section. The gameState resets and then comes back to the serve state.



3) 

```
if(playerScore === 5 || computerScore === 5){
  gameState="over";
  text("Game over", 170, 180);
  text("Press 'R' to restart",165, 227);
  }

  if(keyDown("r")&& gameState==="over"){
  gameState="serve";
  computerScore=0;
  playerScore=0;
  }
```



Whenever someone's score is 5 and the gameState is over, then a text will be displayed.

If we are pressing the "r" key and the gameState is over then the state should reset to serve and the computer and player should go back to being 0.



# Class 7

1) 

```
if(ball.isTouching(playerPaddle)) {
   playSound("sound://category_explosion/melodic_loss_6.mp3");
  }
```

Whenever the ball touches the playerPaddle, it will make a sound.



2) 

```
if (keyWentDown("K")) {
playerPaddle.setAnimation("player_kick");
}

if (keyWentDown("A")) {
 playerPaddle.setAnimation("player");
 }


```

This is for giving the transition between animations.



# Class 8

1)

```
var trex=createSprite(200,340,50,50);
trex.setAnimation("trex");
```

We are creating a new sprite to be seen on the canvas and we are giving its positions, height and width.

We are also putting a costume on the sprite, so it can seem more presentable.



2) 

```
trex.velocityY=trex.velocityY+0.8;
```

We are giving the trex gravity, so whenever it jumps, it will come back on the ground.



3)

```
trex.collide(ground);
```

This creates a barrier, so the trex doesn't go off the canvas.

# Class 9

1) 

```
if (ground.x<0) {
ground.x=ground.width/2;
}
```

This is a command, so that the ground keeps repeating over and over again.



2)

```
 trex.scale = 0.7;
```

This determines the size of the trex.



3) 

```
console.log(ground.x);
```

This is for the debug console. To know the value of the ground in the x-axis.



# Class 10

1) 

```
var invisbleGround = createSprite(200,395,345,10);
invisbleGround.visible=false;
```

This is a  command to make something invisible on the canvas. 



2) 

```
console.log(trex.y);
```

This is for knowing the position of the trex on the y axis.

# Class 11

1) 

```
var rand = randomNumber(1,100);
console.log(rand);
```

This creates frames for the sprites. By the help of this command, the computer can display random outputs on the canvas.



2)

```
 if (World.frameCount%60===0) {
clouds.y=randomNumber(280,300);
}    
```

This is when we have a frame count of 100 and 60% will be eliminated.

The other command is for making the clouds at different heights on the y-axis.



# Class 12



1) 

```
console.log("hello" + "bye");
```

This is for showing something on the debug console.



2) 

```
obstacles.lifetime = 134;
```

This is when we're giving an infinite amount of memory to the sprite.



3) 

```
obstacles.setAnimation("obstacle" + rand);
```

This command is when picking an animation and the sprite has many different costumes. The "rand" helps it be any costume.

4) 

```
cloud.depth = trex.depth;
trex.depth = trex.depth + 1;
```

This means that whenever the trex and clouds should not merge with each other and the trex depth should always greater than the clouds.



# Class 13

1) 

```
var PLAY = 1;
var END = 0;
var gameState = PLAY;
```

We are writing it in capitals because these are the variables which holds the constant value.  We are writing gameState as play because everytime we press the space key, it comes back in the play state.

2) 

```
var ObstaclesGroup = createGroup();
var CloudsGroup = createGroup();
```

We are giving this command because there are many costumes in each sprite, so we are giving the computer the decision to choose any costume.



3) 

```
if(gameState === PLAY){
    //move the ground
    ground.velocityX = -6;
  }

  else if(gameState === END) {
    ground.velocityX = 0;
    ObstaclesGroup.setVelocityXEach(0);
    CloudsGroup.setVelocityXEach(0);

  }
```

This is when the computer is in either in the play state or the end state.  When the game is in the play state, then the velocity is set as -6 because it should move backwards. But if the game is in end state, then the ground should stop moving and each and every obstacle and cloud should stop moving as well.



4) 

```
count = Math.round(World.frameCount/4);
text("Score: "+ count, 250, 100);
```

Whatever, framecount the computer is doing, it has to be divided by 4 otherwise the count on the screen will keep on going at a very fast pace. We are giving a mathematical command, to display the scores along with count of the frames done by computer. 



5) 

```
ObstaclesGroup.add(obstacle);
CloudsGroup.add(cloud);
```

We want the obstacles and clouds throughout the game, so we are keeping this command inside the function spawnObstacles and spawnClouds respectively.



# Class 14

1)

```
 trex.setCollider("circle",0,0,50);
 trex.debug=false;
```

We are creating an invisible radius around the trex, so that we understand the collision whenever it touches the obstacle.

2)

```
 console.log(gameState);
```

This is for printing the gameState on the debug console.

3)     

```
var gameOver = createSprite(200,200);
//setting an animation
gameOver.setAnimation("gameOver");

//setting the size
gameOver.scale=0.6;
 //creating a new sprite
 var restart = createSprite(200,240);
//setting an animation
restart.setAnimation("restart");

//setting a size
restart.scale=0.6;
```

We are creating a new sprite for game over, setting an animation and adjusting the size. We are also doing the same thing for the restart button.



# Class 15

1)        

```
 if (count > 0&& count%100===0) {
//playing a sound
playSound("checkPoint.mp3");
}
```

This is means that whenever the score reaches 100, it should play a sound.



2) 

```
if(keyDown("space") && trex.y >= 359){
 trex.velocityY = -12 ;
 playSound("jump.mp3");
  }
```

This means whenever the trex jumps, it should play another sound.



3)           

```
if(ObstaclesGroup.isTouching(trex)){
gameState = END;
//playing a sound
playSound("die.mp3");
}
```

Whenever the trex touches an obstacle, it should a dying sound.

4) 

```
obstacle.velocityX = -(6+3*count/100);
```

This means we are increasing the speed of the game every time, it hits 100.



# Class 16

1) 

```
trex.setCollider("circle",0,0,30);
```

Setting a radius between for the trex. So, we can understand how much space there is left between the trex and obstacles.



2)

```
 if(mousePressedOver(restart)) {
  reset();
  }
```

This means that whenever we press the restart button, it will go back to reset function.



3) 

```
function reset(){
//the first gameState of the game.
gameState=PLAY;

//the animation
trex.setAnimation("trex");

//reseting the score
count=0;

//destroying both of the groups
ObstaclesGroup.destroyEach();
CloudsGroup.destroyEach();

//making both of the sprites invisible.
gameOver.visible=false;
restart.visible=false;  

}
```

This means that the gameState should be play, the animation for the trex go back to being normal, the score should be 0, the obstacles and clouds should be destroyed  and the restart button and gameOver should be invisible.



# Class 17

1)

```
 function preload(){
  trex_running = loadAnimation("trex1.png","trex3.png","trex4.png");
  trex_collided = loadImage("trex_collided.png");

  groundImage = loadImage("ground2.png")
}
```

Loading the images on the p5 editor. We are using all these things because it is used inside the library. It is only used for loading sounds, animations and images.



2)

```
 trex = createSprite(50,180,20,50);
 trex.addAnimation("running", trex_running);
 trex.scale = 0.5;
```

In P5 editor, we use addAnimation instead of setAnimation. We are also putting the tag there so the computer can understand what we mean by "running".



3)

```
 var trex, trex_running, trex_collided;
 var ground, invisibleGround, groundImage;
```



We write the variables like this in P5 instead of writing it like var object=createSprite();. Along with the variable, we are also adding the tag.



# Class 18



1) 

```
var cloudsGroup, cloudImage;
var obstaclesGroup, obstacle1, obstacle2, obstacle3, obstacle4, obstacle5, obstacle6;

var score;
```



We are creating variables for the cloud and obstacle group. We are also creating it for the images. In P5 editor, we write score instead of count.



2)

```
function preload(){
  trex_running = loadAnimation("trex1.png","trex3.png","trex4.png");
  trex_collided = loadImage("trex_collided.png");

  groundImage = loadImage("ground2.png");

  cloudImage = loadImage("cloud.png");

  obstacle1 = loadImage("obstacle1.png");
  obstacle2 = loadImage("obstacle2.png");
  obstacle3 = loadImage("obstacle3.png");
  obstacle4 = loadImage("obstacle4.png");
  obstacle5 = loadImage("obstacle5.png");
  obstacle6 = loadImage("obstacle6.png");
}


```

​      This is means that we are loading all of the images in P5 also because it is mentioned in the library.



3) 

```
switch(rand) {
      case 1: obstacle.addImage(obstacle1);
              break;
      case 2: obstacle.addImage(obstacle2);
              break;
      case 3: obstacle.addImage(obstacle3);
              break;
      case 4: obstacle.addImage(obstacle4);
              break;
      case 5: obstacle.addImage(obstacle5);
              break;
      case 6: obstacle.addImage(obstacle6);
              break;
      default: break;
```

This means that the costumes should keep changing and breaking. We use this instead of the rand command.



# Class 19

1) 

```
gameOver = createSprite(300,100);
 gameOver.addImage(gameOverImg);

 restart = createSprite(300,140);
 restart.addImage(restartImg);
```



We are creating the gameOver sprite and adding the image to it.

We are creating the restart sprite and adding the image to it.

 

2)

```
 gameOver.scale = 0.5;
 restart.scale = 0.5;
```

Adjusting the size for each sprite.



3) 

```
gameOver.visible = false;
restart.visible = false;
```

Making both sprites invisible.

# Class 20

1) 

```
function setup() {
  createCanvas(1200,800);
  fixedRect = createSprite(600, 400, 50, 80);
  fixedRect.shapeColor = "green";
  fixedRect.debug = true;
  movingRect = createSprite(400,200,80,30);
  movingRect.shapeColor = "green";
  movingRect.debug = true;
}
```

We are creating the canvas, creating and giving a color to the fixed rectangle and the moving rectangle and we are also putting the debug control, so we can see what mistakes we have made in the debug control.



2) 

```
if (movingRect.x - fixedRect.x < fixedRect.width/2 + movingRect.width/2
      && fixedRect.x - movingRect.x < fixedRect.width/2 + movingRect.width/2
      && movingRect.y - fixedRect.y < fixedRect.height/2 + movingRect.height/2
      && fixedRect.y - movingRect.y < fixedRect.height/2 + movingRect.height/2) {
    movingRect.shapeColor = "red";
    fixedRect.shapeColor = "red";
  }
  else {
    movingRect.shapeColor = "green";
    fixedRect.shapeColor = "green";
```

Making a command that helps the color of both turn into red if they collide into each other and if they are away from each other then green.

# Class 21

1) 

```
function isTouching(object1,object2){
  if (object1.x - object2.x < object2.width/2 + object1.width/2
    && object2.x - object1.x < object2.width/2 + object1.width/2
    && object1.y - object2.y < object2.height/2 + object1.height/2
    && object2.y - object2.y < object2.height/2 + object1.height/2) {
    
    return true;
  }
  else {
    return false;
  } 
}
```

This means that if the object1 is touching the object2, the then its color will be red. But , if its away then it will be green. That's why, we are are writing else there.

2) 

```
  gameObject1 = createSprite(100, 100, 50, 50);
  gameObject1.shapeColor = "green";
  gameObject2 = createSprite(200, 100, 50, 50);
  gameObject2.shapeColor = "green";
  gameObject3 = createSprite(300, 100, 50, 50);
  gameObject3.shapeColor = "green";
  gameObject4 = createSprite(400, 100, 50, 50);
  gameObject4.shapeColor = "green";
```

Here, we are creating all the game objects, we gave it's dimensions and its color as green.



# Class 22

1) 

```
const Engine = Matter.Engine;
const World= Matter.World;
const Bodies = Matter.Bodies;
```

Const means constant. Engine means where the physics conditions are applied. World is used for adding the physical world to the object and bodies is used for adding a physical body to the object.

2)  

```
 var ground_options ={
   isStatic: true
    }
```

This is for making the ground not move. To be stable, for the entire program.

3)  

```
 var ball_options ={
   restitution: 1.0
    }
```

This determines how bouncy the ball is.

4) 

```
function draw(){
    background(0);
    Engine.update(engine);
    rectMode(CENTER);
    rect(ground.position.x,ground.position.y,400,20);

    ellipseMode(RADIUS);
    ellipse(ball.position.x, ball.position.y, 20, 20);
}
```

The  Engine.update(engine)  is for updating the position of the ball every now and then. The next command means that the rectangle should be placed in the middle of the screen and it also gives the proper positions. The ellipseMode(RADIUS) helps us in changing the  property of an object and gives the proper positions.



# Class 23

1)  

```
class Box {
  //used for intializing an object
  constructor(x, y, width, height) {
    var options = {
      //bounciness of an object
        'restitution':0.8,
        //the opisite force which applies on the object
        'friction':0.3,
        //total mass/total weight of an object
        'density':1.0
    }
    this.body = Bodies.rectangle(x, y, width, height, options);
    this.width = width;
    this.height = height;
    
    World.add(world, this.body);
  }
  display(){
    var pos =this.body.position;
    var angle = this.body.angle;
    //its going to adjust the different position of an object
    push();
    //changing the position
    translate(pos.x, pos.y);
    //when they collide, they bounce off each other and are different angles.
    rotate(angle);
    //for placing the rectangle in the middle of the canvas
    rectMode(CENTER);
    //the canvas is white
    fill(255);
    //the rectangles width/height
    rect(0, 0, this.width, this.height);
    //for reseting all the settings.
    pop();
  }
};

```

This a completely different class created for the box. We are writing class here because it is a blueprint for the entire thing. The constructor means to initialize an object.

2) 

```
 box1 = new Box(200,300,50,50);
 box1.display();
```

We are creating new sprites in the function setup and then displaying them on the screen in function draw.

3) 

```
console.log(box2.body.position.x);
console.log(box2.body.position.y);
console.log(box2.body.angle);

```

This is so we can see the positions of the box  on the debug console.

# Class 24

1) 

```
class Bird {
    constructor(x, y) {
      var options = {
        'density':1.5,
        'friction': 1.0,
        'restitution':0.5
      };
      this.body = Bodies.rectangle(x, y, 50, 50, options);
      this.width = 50;
      this.height = 50;
      World.add(world, this.body);
    };
    display(){
      var pos = this.body.position;
      pos.x = mouseX;
      pos.y = mouseY;
      var angle = this.body.angle;
  
      push();
      translate(pos.x, pos.y);
      rotate(angle);
      strokeWeight(3);
      stroke('blue')
      fill('red')
      rectMode(CENTER)
      rect(0, 0, this.width, this.height);
      pop();
    };
  };
```

We are creating blueprints for the bird, pig and log. We putting the options on there and then putting the density(how thorough it is), the friction(the opposite force which applies on the object) and the restitution(the bounciness of an object).  Then in the display category, we are putting the position as the mouse, so it moves where the mouse moves. Then we are adding the angle. Then adding the push(positions), translate, rotate, color, where its going to be placed and the pop which means resetting all the settings.

# Class 25

1) 

```
class BaseClass{
    constructor(x, y, width, height, angle) {
        var options = {
            'restitution':0.8,
            'friction':1.0,
            'density':1.0
        }
        this.body = Bodies.rectangle(x, y, width, height, options);
        this.width = width;
        this.height = height;
         this.image= loadImage("sprites/base.png");
        World.add(world, this.body);
      }
      display(){
        var angle = this.body.angle;
        push();
        translate(this.body.position.x, this.body.position.y);
        rotate(angle);
        imageMode(CENTER);
        image(this.image, 0, 0, this.width, this.height);
        pop();
      }
}
```

making a parent file and adding all the common features in it.



2)

```
class Bird extends BaseClass{
  constructor(x,y){
    super(x,y,50,50);
    this.image = loadImage("sprites/bird.png");
  }
  display(){
    this.body.position.x = mouseX;
    this.body.position.y = mouseY;
    super.display();
  }
}
```

Extends is a reference to the parent file.

super gives the authorisation to use all the properties and functions of the parent class.

# class 26

1 . pwd-stands for present working directory.

1. ls- lists down all the files.
2. mkdir class-26 -makes new folder at given location.
3. cd- used to change location of work.
4. git clone-helps in making exact copy of file needed.
5. git add-used for adding changes made in file.
6. git commit- specifically changes a few things in the program.
7. git status - seeing changes made till date.

# Class 27

```
class Chain{
    constructor(bodyA, bodyB){
        var options = {
            bodyA: bodyA,
            bodyB: bodyB,
            stiffness: 0.04,
            length: 10
        }
        this.chain = Constraint.create(options);
        World.add(world, this.chain);
    }

    display(){
        var pointA = this.chain.bodyA.position;
        var pointB = this.chain.bodyB.position;
        strokeWeight(4);
        line(pointA.x, pointA.y, pointB.x, pointB.y);
    }
    
}
```

1. Creating a chain.
2. Attaching one side to bird and other side to log6.
3. adding a streachy limit to the chain using constraint.
4. adding weight to the chain.
5. giving x and y coordinates to the chain using line.

```
 log6 = new Log(230,180,80, PI/2);
    chain = new Chain(bird.body,log6.body);
```

1. Defining the log and chain.

```
var backgroundImg,platform ;
```

1. creating a platform on which angry bird and sling shot is kept.



# class 28

1. ```
   class Slingshot{
   ```

   ```
       constructor(bodyA, pointB){
   ```

   ```
           var options = {
   ```

   ```
               bodyA: bodyA,
   ```

   ```
               pointB: pointB,
   ```

   ```
               stiffness: 0.04,
   ```

   ```
               length: 10
   ```

   ```
           }
   ```

   ```
           this.pointB = pointB
   ```

   ```
           this.sling = Constraint.create(options);
   ```

   ```
           World.add(world, this.sling);
   ```

   ```
       }
   ```

   ```
   
   ```

   ```
       fly(){
   ```

   ```
           this.sling.bodyA = null;
   ```

   ```
       }
   ```

   ```
   
   ```

   ```
       display(){
   ```

   ```
           if(this.sling.bodyA){
   ```

   ```
               var pointA = this.sling.bodyA.position;
   ```

   ```
               var pointB = this.pointB;
   ```

   ```
               strokeWeight(4);
   ```

   ```
               line(pointA.x, pointA.y, pointB.x, pointB.y);
   ```

   ```
           }
   ```

   ```
       }
   ```

   ```
       
   ```

   ```
   }
   ```

   Creating a rubberband like slingshot attached to bird and fixed point.

   Creating a stiffness command in var options so that it offers some resistance .

   Stroke weight is giving a weight so that when it hits the blocks it is heavy enough to drop them.

    Constraint is an opposite  force which is applied to make the object flexible and get it back to its original position.

2.

```
function mouseDragged(){
    Matter.Body.setPosition(bird.body, {x: mouseX , y: mouseY});
}


function mouseReleased(){
    slingshot.fly();
}
```

Giving a command so that if the mouse is dragged over the bird it will drag the bird along.

if the mouse is released the bird should fly off .

# class 29-33

```
function keyPressed(){
    // keycode 32 is the space key
    if(keyCode === 32 && bird.body.speed < 1){
       bird.trajectory = [];
       Matter.Body.setPosition(bird.body,{x:200, y:50});
       slingshot.attach(bird.body);
    }
}
// not syncing it with the internet data
async function getBackgroundImg(){
    // wating for permission from the website to take the information
    var response = await fetch("http://worldtimeapi.org/api/timezone/Asia/Kolkata");
    // JSON is the format of information in which website is written
    var responseJSON = await response.json();

    var datetime = responseJSON.datetime;
    var hour = datetime.slice(11,13);
    
    if(hour>=06 && hour<=17){
        bg = "sprites/bg.png";
    }
    else{
        bg = "sprites/bg2.jpg";
    }

    backgroundImg = loadImage(bg);
   console.log(backgroundImg);
}
```

1.if space key is pressed and the speed of the bird is more than 1 then we need a trajectory to be made 

2.JSON is JavaScript Object Notation.it is the format in which websites are written.

1. API calls is Application Programming Interface. it gives the information we are looking for.
2. response JSON will extract all the information we are looking for from the website.



```
//base class is the parent programming
class BaseClass{
  //constructor is used for initialising an object
    constructor(x, y, width, height, angle) {
        var options = {
            'restitution':0.8,
            'friction':1.0,
            'density':1.0
        }
        this.body = Bodies.rectangle(x, y, width, height, options);
        this.width = width;
        this.height = height;
        this.image = loadImage("sprites/base.png");
        World.add(world, this.body);
      }
      display(){
        var angle = this.body.angle;
        //for changing positions of an object
        push();
        //updating all the positions
        translate(this.body.position.x, this.body.position.y);
        rotate(angle);
        //keeping image in between no matter what is the size of the canvas
        imageMode(CENTER);
        image(this.image, 0, 0, this.width, this.height);
        //resetting everything
        pop();
      }
}
```

1.Base class is the parent class which has all the properties 

2.restitution is the bounciness.

1. pop is for resetting everything.
2. translate is used for updating all the positions.

5.push is for changing positions of an object

```
class SlingShot{
    constructor(bodyA, pointB){
        var options = {
            bodyA: bodyA,
            pointB: pointB,
            stiffness: 0.04,
            length: 10
        }
        this.sling1 = loadImage('sprites/sling1.png');
        this.sling2 = loadImage('sprites/sling2.png');
        this.sling3 = loadImage('sprites/sling3.png');
        this.pointB = pointB
        this.sling = Constraint.create(options);
        World.add(world, this.sling);
    }
    attach(body){
        this.sling.bodyA = body;
    }
    
    fly(){
        this.sling.bodyA = null;
    }

    display(){
        image(this.sling1,200,20);
        image(this.sling2,170,20);
        if(this.sling.bodyA){
            var pointA = this.sling.bodyA.position;
            var pointB = this.pointB;
            push();
            
            stroke(48,22,8);
            if(pointA.x < 220) {
                strokeWeight(7);
                line(pointA.x - 20, pointA.y, pointB.x -10, pointB.y);
                line(pointA.x - 20, pointA.y, pointB.x + 30, pointB.y - 3);
                image(this.sling3,pointA.x -30, pointA.y -10,15,30);
            }
            else{
                strokeWeight(3);
                line(pointA.x + 25, pointA.y, pointB.x -10, pointB.y);
                line(pointA.x + 25, pointA.y, pointB.x + 30, pointB.y - 3);
                image(this.sling3,pointA.x + 25, pointA.y -10,15,30);
            }
           
            
            pop();
        }
    }
    
}
```

1. Creating a blue print of slingshot which has the properties of rubber band.

2. Giving Stiffness ,constraint so that when ever the objects are stretched they come back to their original position because of the forces working on it

3. Giving Stroke Weight to the object so that it can be stretched properly

4. using multiple lines to create a sling shot and adjusting the same on the screen 

5. attach-it is used for keeping the angry bird on the rubber band

6. fly- it is used for making the angry bird fly whenever the slingshot is dragged and then released

   

# class 34 - 41 - car racing game

```
class Form {

  constructor() {
    this.input = createInput("Name");
    this.button = createButton('Play');
    this.greeting = createElement('h2');
    this.title = createElement('h2');
    this.reset= createButton('Reset');
  }
  hide(){
    this.greeting.hide();
    this.button.hide();
    this.input.hide();
    this.title.hide();
  }

  display(){
    this.title.html("Car Racing Game");
    this.title.position(displayWidth/2 - 50, 0);

    this.input.position(displayWidth/2 - 40 , displayHeight/2 - 80);
    this.button.position(displayWidth/2 + 30, displayHeight/2);
2
    this.button.mousePressed(()=>{
      this.input.hide();
      this.button.hide();
      player.name = this.input.value();
      playerCount+=1;
      player.index = playerCount;
      player.update();
      player.updateCount(playerCount);
      this.greeting.html("Hello " + player.name)
      this.greeting.position(displayWidth/2 - 70, displayHeight/4);
    });
    this.reset.mousePressed(()=>{
    player.updateCount(0);
    game.update(0);
    })

  }
}
```

1. we are creating a form where the players will write their name
2. constructing the input box,play button,title,reset button,greeting
3. create Element is a part of html used for designing the page
4. hiding everything on screen as soon as the game starts
5. giving positions to different buttons and making it work with the help of mouse pressed commands 
6. creating player index to track the players information
7. updating the player count and name of the player
8. creating a reset button which will reset the database



```

class Game {
  constructor(){

  }

  getState(){
    var gameStateRef  = database.ref('gameState');
    gameStateRef.on("value",function(data){
       gameState = data.val();
    })

  }

  update(state){
    //keeping it empty bcoz no details are knoew at this particular time 
    database.ref('/').update({
      gameState: state
    });
  }

  async start(){
    if(gameState === 0){
      player = new Player();
      //awaiting for the player count and updating it once for every player
      var playerCountRef = await database.ref('playerCount').once("value");
      //data only once has to be saved for one player 
      if(playerCountRef.exists()){
        playerCount = playerCountRef.val();
        player.getCount();
      }
      form = new Form()
      form.display();
    }

    car1 = createSprite(100,200);
    car1.addImage("car1",car1_img);
    car2 = createSprite(300,200);
    car2.addImage("car2",car2_img);
    car3 = createSprite(500,200);
    car3.addImage("car3",car3_img);
    car4 = createSprite(700,200);
    car4.addImage("car4",car4_img);
    cars = [car1, car2, car3, car4];
  }

  play(){
    form.hide();
    
    Player.getPlayerInfo();
    player.getCarsAtEnd();
    
    if(allPlayers !== undefined){
      //different shades of colours to balance the colours on screen 
      background(rgb(198,135,103));
      image(track, 0,-displayHeight*4,displayWidth, displayHeight*5);
      
      //var display_position = 100;
      
      //index of the array
      var index = 0;

      //x and y position of the cars
      var x = 175 ;
      var y;

      for(var plr in allPlayers){
        //add 1 to the index for every loop
        index = index + 1 ;

        //position the cars a little away from each other in x direction
        x = x + 200;
        //use data form the database to display the cars in y direction
        y = displayHeight - allPlayers[plr].distance;
        cars[index-1].x = x;
        cars[index-1].y = y;
       // console.log(index, player.index)

       
        if (index === player.index){
          stroke(10);
          fill("red");
          // ellipse is used for changing the shape.example rectangle to circle
          ellipse(x,y,60,60);
          //camera command to view the objects from different angle 
          cars[index - 1].shapeColor = "red";
          camera.position.x = displayWidth/2;
          camera.position.y = cars[index-1].y;
        }
       
        //textSize(15);
        //text(allPlayers[plr].name + ": " + allPlayers[plr].distance, 120,display_position)
      }

    }

    if(keyIsDown(UP_ARROW) && player.index !== null){
      player.distance +=10
      player.update();
    }

    if(player.distance > 3860){
      gameState = 2;
      //rank needs to be given and increased 
      player.rank +=1
      //updating the rank 
      Player.updateCarsAtEnd(player.rank)
    }
   
    drawSprites();
  }

  end(){
    console.log("Game Ended");
    console.log(player.rank);
  }
}

```

1. creating a blueprint for the game and constructing it 
2. giving the game states ,referring it to the database,on is used for extracting the information from the firebase and showing the output on screen
3. update -used for updating the database for the game state
4. async start - creating the section for the game state 0 that is the starting of the game , referring the player count to the database every time one player enters their name , writing the player count inside the value box,creating a new form and displaying it
5. creating four cars and adding image to it 
6. play- it is made for getting the player information ,creating index,camera commands ,up arrow key to move the car and calculate the distance,updating the game state and changing the game state to end 



```
class Player {
  constructor(){
    this.index = null;
    this.distance = 0;
    this.name = null;
    this.rank = null;
  }

  getCount(){
    // referring to the player count on the firebase database
    var playerCountRef = database.ref('playerCount');
    playerCountRef.on("value",(data)=>{
      playerCount = data.val();
    })
  }

  updateCount(count){
    database.ref('/').update({
      playerCount: count
    });
  }

  update(){
    //creating index for player name and keep on adding when some new player joins 
    var playerIndex = "players/player" + this.index;
    database.ref(playerIndex).set({
      name:this.name,
      //calculating the distance 
      distance:this.distance
    });
  }

  static getPlayerInfo(){
    var playerInfoRef = database.ref('players');
    playerInfoRef.on("value",(data)=>{
      allPlayers = data.val();
    })
  }

  getCarsAtEnd() {
    database.ref('CarsAtEnd').on("value",(data)=>{
      //updating the rank of the player 
      this.rank = data.val();
    })
  }
// making the rank stable on screen 
  static updateCarsAtEnd(rank) {
    // keeping it empty because everything needs to be updated
    database.ref('/').update({
      CarsAtEnd:rank
    })
  }
}


```



```

  var canvas, backgroundImage;

var gameState = 0;
var playerCount;
var allPlayers;
var distance = 0;
var database;

var form, player, game;

var cars, car1, car2, car3, car4;

var track, car1_img, car2_img, car3_img, car4_img;

function preload(){
  track = loadImage("../images/track.jpg");
  car1_img = loadImage("../images/car1.png");
  car2_img = loadImage("../images/car2.png");
  car3_img = loadImage("../images/car3.png");
  car4_img = loadImage("../images/car4.png");
  ground = loadImage("../images/ground.png");
}

function setup(){
  // adjusting the canvas size according to the size of the screen
  canvas = createCanvas(displayWidth - 20, displayHeight-30);
  //creating the database and referring it to firebase database 
  database = firebase.database();
  //starting the new game for the players 
  game = new Game();
  game.getState();
  game.start();
}


function draw(){
  //after 4 player the closed room will be created for players 
  if(playerCount === 4){
    //updating the game 
    game.update(1);
  }
  if(gameState === 1){
    //1 is for the start of the game and clear will remove the other data which is not needed in the game 
    clear();
    // start the game section 
    game.play();
  }// if the game has ended the game state will shift to 2=end
  if(gameState === 2){
    game.end();
  }
}

```

# Class 42

1. Pong : variables, storing numbers, strings, conditional programming (if-else), for loop, functions, game state etc.

   conditional programming - used for controling the objects with the help of if and else condition 

2. Trex : Creating infinitely scrolling ground, arrays, switch statements, library, writing own library, DRY, etc. 

   switch statement used as a pause button to stop something from repeatedly coming 

3. Angry Birds : Classes, objects, physics engine, calling an API, Code Readability, Writing structured code etc. 

   API - used for getting the exact information by not letting us know the source of it 

4. Car Racing Game: Databases, reading and writing to a database etc.

database - creating a database inside fire base and merging it 

# Class 43-48

```
// creating the gamestates
var PLAY = 1;
var END = 0;
var gameState = PLAY;

var food,foodGroup;

var dory,doryImg;
var back,backImage;
var obstaclesGroup,bag1,bag2,bottle1,bottle2;

var score=0;

var gameOver,gameOverImg,restartImg, restart;


function preload(){
  bag1=loadImage("bag1.jpg");
  bag2=loadImage("bag2.jpg");
  bottle1=loadImage("bottle1.jpg");
  bottle2=loadImage("bottle2.png");
  
  doryImg=loadImage("dory.jpg");
  
  backImage=loadImage("background1.jpg");
  
  gameOverImg=loadImage("gameOver.png");
  
  restartImg = loadImage("restart.png");
}

function setup() {
  createCanvas(600, 400);

  score = 0;
  
  //adding the background
    back = createSprite(200,180,400,20);
  back.addImage("back",backImage);
  back.x = back.width /2;
  back.velocityX = -6;
  back.scale=1.2;
  
  //making the dory
  dory= createSprite(100,350,40,80);
  dory.addImage("dory",doryImg);
  dory.scale = 0.3;
  
  
  gameOver = createSprite(300,100);
  gameOver.addImage(gameOverImg);
  
  restart = createSprite(300,140);
  restart.addImage(restartImg);
  
  gameOver.scale = 0.5;
  restart.scale = 0.5;

  gameOver.visible = false;
  restart.visible = false;
  
  //creating the groups
  obstaclesGroup = new Group();
 foodGroup=new Group();

}

function draw() {
   
  background(255);
  background.scale=2.5;
  textSize(30);
  text("Score: "+ score, 500,50);
  fill="white";
  
  
  
  if (gameState===PLAY){
    //the background should move faster after every 100 points
    back.velocityX = -(6 + 3*score/100);
  
    if(keyDown("left_arrow") ) {
      dory.velocityX=-3;
    }
    if (keyDown("up_arrow")){
      dory.velocityY=-3;
    }
  if (keyDown("down_arrow")){
    dory.velocityY=3;
  }
    if (keyDown("right_arrow")){
      dory.velocityX=3;
    }
    

  //making the background continuous
    if (back.x < 0){
      back.x = back.width/2;
    }
  
    spawnObstacles();
    
    //if dory eats the food the score should increase
  if (foodGroup.isTouching(dory)){
    score=score+1;
  }
  //if dory touches the plastic she dies 
    if(obstaclesGroup.isTouching(dory)){
        gameState = END;
    }
  }
  else if (gameState === END) {
    gameOver.visible = true;
    restart.visible = true;
    
    //set velcity of each game object to 0
    back.velocityX = 0;
    dory.velocityY = 0;
   
    obstaclesGroup.setVelocityXEach(0);
  foodGroup.setVelocityXEach(0);
    
    obstaclesGroup.setLifetimeEach(-1);
    foodGroup.setVelocityEach(0);
   
    if(mousePressedOver(restart)) {
      reset();
    }
  }
  
  
  drawSprites();
}



function spawnObstacles() {
// after every 60 frames an obstacle should be created
  if(frameCount % 60 === 0) {
    var obstacle = createSprite(600,165,10,40);
    obstacle.velocityX = -(6 + 3*score/100);
    
    //generate random obstacles
    var rand = Math.round(random(1,4));
    switch(rand) {
    //adding different images
      case 1: obstacle.addImage(bag1);
              break;
      case 2: obstacle.addImage(bottle2);
              break;
      case 3: obstacle.addImage(bottle1);
              break;
      case 4: obstacle.addImage(bag2);
              break;
      default: break;
    }
    
    //assign scale and lifetime to the obstacle           
    obstacle.scale = 0.1;
    obstacle.lifetime = 300;
    //add each obstacle to the group
    obstaclesGroup.add(obstacle);
  }
}
function spawnFood(){
//after every 60 frames food should be created
  if(frameCount % 60 === 0) {
    var food = createSprite(300,165,20,20);
    food.velocityX=-4;
    food.shapeColor="white";
   }
  food.lifetime=200;
  foodGroup.add(food);
  
}
function reset(){
//if the reset button is pressed the game should start again
  gameState = PLAY;
  gameOver.visible = false;
  restart.visible = false;
  
  obstaclesGroup.destroyEach();
  
  score = 0;
  
}
```

# Class 49

1. HTML (Hypertext Markup Language) and CSS (Cascading Style Sheets).
2. HTML - Hyper Text Markup Language is very similar to Markdown in some ways.
3. HTML is used to create content which is displayed on web pages.
4. We use <h1> tags to create a BIG header. <h2>, <h3>, <h4> tags could be used to create SMALLER headers. Guide the student to create header using <h1> tag inside html body
5. We use <a> tag to create hyperlinks. Let's create two hyperlinks - Projects and About
   1. <a> tag has an attribute called 'href' (hypertext reference) which is used to point the tag to other pages. Guide the student to use 'href' attribute to point it to hyperlinks
   2. We use <img/> tag to add images. <img/> is a self-closing tag - we do not need opening and closing tags for < img/>

# Class 50

```
h1 {
    color: white;
}

/* * {
    border: solid;
} */

.header{
    background-color: cadetblue;
    display: flex;
    justify-content: space-between;
}

.site-description{
    display: flex;
    flex-direction: column;
    justify-content: first baseline;
}

.grid{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

.footer{
    display: flex;
    justify-content: flex-end;
}

p,h2{
    text-align: center;
}
```

1. h1 ,h2,h3 are font sizes with h1 being the largest and h3 the smallest.

2. site-description is used for designing the whole page and managing the text on the lower half.

3. flex is the top part of any website .

4. grid is used to space the images properly

5. p stands for paragraph.

6. text align is used to space the words properly

7. justify content will help[ in giving proper spacing between text

   

```
 <link rel ="stylesheet" 
         type="text/css" 
         href="style.css"    />

</head>

<body>
    <div class="header">
    <h1>   Student Name          </h1>
    <div class="menu">
        <a href="index.html" > PROJECTS </a>
        <a href="aboutme.html" > ABOUT ME  </a>
    </div>
</div>

<h2> These are some games designed by me</h2>
<p>  Games use p5.js, p5.play and matter.js libraries in javascript   </p>


<div class="grid">
 <div class="item" >
    <a href="https://editor.p5js.org/whitehatjr/present/ePJrHCACM"><img src="https://via.placeholder.com/300"/></a>
    <p>   TREX RUNNER GAME   </p>
 </div>
 
```

1. link is used for merging html and css coding .

2. href is html refference.

3. div is used for creating the big boxes.

4. div class is for creating a blueprint.

5. if <div>is the opening then <div/> is the closing.

   # Class 52

```
h1 {
 color: white;
 margin-left:30px;
}

/* * {
    border: solid;
} */

.header{
    background-color: rgb(85, 177, 214);
    display: flex;
    justify-content: space-between;
  
}

.site-description{
    display: flex;
    flex-direction: column;
    justify-content: first baseline;
}

.grid{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-evenly;
}

.footer{
    display: flex;
    justify-content: flex-end;
}

p,h2{
    text-align: center;
}
body{
    background-color:rgb(128,128,128);
}
<!DOCTYPE HTML>
<html>
    <head>
<title>  My Portfolio Page         </title>
   <link rel ="stylesheet" 
         type="text/css" 
         href="style.css"    />

</head>

<body>
    <div class="header">
    <h1>   Anushka Mishra        </h1>
    <div class="menu">
      
        <a href="https://anushka3800.whjr.site/" > ABOUT ME  </a>
    </div>
</div>




<h2> These are some games designed by me</h2>
<p>  Games use p5.js, p5.play and matter.js libraries in javascript   </p>


<div class="grid">
 <div class="item" >

    <a href="https://editor.p5js.org/whitehatjr/present/ePJrHCACM"><img src="trex1.png"/></a>

    <p>   TREX RUNNER GAME   </p>
  
 </div>
 


 <div class="item" >
    <a href = "#"><img src="https://via.placeholder.com/300"/></a>
        <p>Name of game 2</p>
 </div>
 
 
 <div class="item" >
    <a href = "#"><img src="https://via.placeholder.com/300"/></a>
        <p>Name of game 3</p>
 </div>


 <div class ="item">
    <a href = "#"><img src="https://via.placeholder.com/300"/></a>
    <p>Name of game 4</p>
 </div>

 <div class ="item">
    <a href = "#"><img src="https://via.placeholder.com/300"/></a>
        <p>Name of game 5</p>

 </div>
 
 <div class ="item">
    <a href = "#"><img src="https://via.placeholder.com/300"/></a>
        <p>Name of game 6</p>

 </div>
 <div class ="item">
    <a href = "#"><img src="https://via.placeholder.com/300"/></a>
        <p>Name of game 7</p>

 </div>

 
</div>


<div class="footer">
    <a href="#"><img src="fb.png" width=50 height=50/></a>
    <a href="#"><img src="insta.png" width=50 height=50/></a>
    <a href="#"><img src="youtube.png" width=50 height=50/></a>

</div>

</body>

    </html>

```

# 