# Miss-you-project
import processing.pdf.*;

int amount =3; 
int[][] state= new int[amount][amount];
PImage img1,img2,img3,img4,img5,img6;
int mx,my;

void setup() {
 size(900,900);
for(int x =0;x< amount; x++){
    for(int y =0;y< amount; y++){
    state[x][y] = int (random(0,8));
  }
  }
  img1 = loadImage("1.jpg");
  img1.resize(width,height);
  img2 = loadImage("2.jpg");
  img2.resize(width,height);
   img3 = loadImage("33.jpg");
  img3.resize(width,height);
  img4 = loadImage("4.jpg");
  img4.resize(width,height);
  img5 = loadImage("5.jpg");
  img5.resize(width,height);
  img6 = loadImage("6.jpg");
  img6.resize(width,height);
   
}

void draw() {
  background(#f1f1f1);
image(img2,0,0);
  float tileW =width/amount;
  float tileH =height/amount;
  fill(#000000);
  noStroke();
ellipseMode(CORNER);

mx= int (map(mouseX,0,width,0, amount));
my = int(map(mouseY,0,height,0, amount));




//ellipseMode(CORNER);
    for(int x =0;x< amount; x++){
    for(int y =0;y< amount; y++){
    
  
  
  if (state[x][y] == 0){
    pushMatrix();
    translate(x*tileW,y*tileH); 
     ellipse(0,0,tileW,tileH);
      popMatrix();
      
    }else if (state[x][y] == 1){
    pushMatrix();
    translate(x*tileW,y*tileH); 
    rect(0,0,tileW,tileH);
    popMatrix();
    
   }else if (state[x][y] == 2){
    pushMatrix();
    translate(x*tileW,y*tileH); 
    triangle(0,0,tileW,tileH,0,tileW);
    popMatrix();
    
  }else if (state[x][y] == 3){
   int sx = int(tileW*x);
   int sy = int(tileH*y);
   int sw = int(tileW);
   int sh = int(tileH);
    
   int dx = sx;
   int dy = sy;
   int dw = sw;
   int dh = sh;

    
    copy(img1,sx,sy,sw,sh,dx,dy,dw,dh);
    
  }else if (state[x][y] == 4){ 
    int sx = int(tileW*x);
   int sy = int(tileH*y);
   int sw = int(tileW);
   int sh = int(tileH);
    
   int dx = sx;
   int dy = sy;
   int dw = sw;
   int dh = sh;

    
    copy(img2,sx,sy,sw,sh,dx,dy,dw,dh);
   // rect(0,0,tileW,tileH);
  
}else if (state[x][y] == 5){
     int sx = int(tileW*x);
   int sy = int(tileH*y);
   int sw = int(tileW);
   int sh = int(tileH);
    
   int dx = sx;
   int dy = sy;
   int dw = sw;
   int dh = sh;

    
    copy(img3,sx,sy,sw,sh,dx,dy,dw,dh);
  }
  else if (state[x][y] == 6){
     int sx = int(tileW*x);
   int sy = int(tileH*y);
   int sw = int(tileW);
   int sh = int(tileH);
    
   int dx = sx;
   int dy = sy;
   int dw = sw;
   int dh = sh;

    
    copy(img4,sx,sy,sw,sh,dx,dy,dw,dh);
  }
   else if (state[x][y] == 7){
     int sx = int(tileW*x);
   int sy = int(tileH*y);
   int sw = int(tileW);
   int sh = int(tileH);
    
   int dx = sx;
   int dy = sy;
   int dw = sw;
   int dh = sh;

    
    copy(img5,sx,sy,sw,sh,dx,dy,dw,dh);
  } 
    
    else if (state[x][y] == 8){
     int sx = int(tileW*x);
   int sy = int(tileH*y);
   int sw = int(tileW);
   int sh = int(tileH);
    
   int dx = sx;
   int dy = sy;
   int dw = sw;
   int dh = sh;

    
    copy(img6,sx,sy,sw,sh,dx,dy,dw,dh);
  }
    
  }

  
  
  
  
  }
  
  
for(int x =0;x< amount; x++){
    for(int y =0;y< amount; y++){
    }
  
}
  
}
void countUp(int x, int y){
  if (state[x][y] < 8) {
    state[x][y]++;
  } else{
    state [x][y]=0;
}
}
void mouseReleased(){
   countUp(mx,my);
 saveFrame("dododo/visual####.jpg");

}
