# weaverAnimation

PImage smileyFace;

int myArray = 20;
// makes 2 different array list, one x and one y
ArrayList x, y;

float r2 = random(200, 300);
float r1 = r2;

void setup() {
  background(255);
  fill(0);
  textSize(32);
  text("Press 'Q' to make more faces.", 50, 100);
  text("Press 'P' to remove faces.", 1500, 100);
  
  x = new ArrayList();
  y = new ArrayList();
  
  for(int i = 0; i < myArray; i++) {
    // adds random items to the array list
    x.add(random(width));
    y.add(random(height));
  }
  println(x);
  imageMode(CENTER);

  size(displayWidth, displayHeight);
  smileyFace = loadImage("smileyFace.png");
}

void draw() {
  imageMode(CENTER);
  image(smileyFace, width/2, height/2, 300, 300);
  if (key == 'q' || key == 'Q') {
  tint(random(0,255), random(0,255), random(0,255));
    for(int i = 0; i < x.size(); i++) {
      // grabs the array values and casts them as floats
      float val1 = (Float) x.get(i);
      float val2 = (Float) y.get(i);
      image(smileyFace, val1, val2, r1, r2);
  }
  }
  if (key == 'p' || key == 'P') {
    // messes with faces
    background(255);
   tint(random(0,255), random(0,255), random(0,255));
    image(smileyFace, mouseX, mouseY, 30, 30);
  }
}
