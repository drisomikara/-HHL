# -HHL
int x =700;
int y =330;
float radius =20;

import ddf.minim.*;
Minim minim;
AudioInput in;
PImage img;



void setup(){
  size(1400,660);
  noStroke();
  smooth();
  ellipseMode(RADIUS);
  img = loadImage("rrl.png");
  minim = new Minim(this);
  in = minim.getLineIn();

}

void draw(){
  
  background(255);
  
  
 //float d = dist (mouseX, mouseY,x,y);
  for(int i=0;i<in.bufferSize();i+=10){
     radius=in.mix.get(i)*300; 
    
     tint(255, radius);
     image(img,0,0);
     
     ellipse(800,330,radius,radius);
     fill(255,202,1,120);
    
   
    ellipse(700,330,radius,radius);
    fill(0,91,177,120);
    
    ellipse(600,330,radius,radius);
    fill(232,2,1,120);
  }
  /*
   if(d> radius){
     radius++;
   }else{
     radius--;
   }
   */
}
