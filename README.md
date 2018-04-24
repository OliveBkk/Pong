# Pong
float deplacementX, deplacementY;
float x, y;

float w, z;

void setup() 
{
 size(400,400);
 background(0);
 x = 200;
 y = 200; 
 deplacementX = 3;
 deplacementY = -3; 
 w = 15;
 z = 60;
}


void draw() 
{
 nettoyer();
 bouger();
 rebondir();
 dessiner();
}


void nettoyer() 
{  
background(0);
}

void dessiner() 
{
  smooth();
  fill(255);
  rect(w,z,25,85);
  fill(255);
  ellipse(x,y,20,20);
}

void bouger() 
{
 x = x + deplacementX;
 y = y + deplacementY;
 z = mouseY;
}

void rebondir() 
{
 
 // si on est trop à droite et que le déplacement horizontal est positif
 if (x > width-10 ) 
 {
   deplacementX = -deplacementX; // inverser la valeur
 }
 

 
 // si on est trop bas et le déplacement vertical est positif
 if (y > width-10 ) 
 { 
   deplacementY = -deplacementY; // rendre négative la valeur
 }
 
 // si on est trop haut et le déplacement vertical est negatif
 if (y < 10 ) 
 {
   deplacementY = -deplacementY; // rendre positive cette valeur
 }
 
 if (x<w+35 && y>z && y<z+85)
  {
   deplacementX = deplacementX*-1.1; // inverser la valeur
 }

 if (x < 10) 
 {
  noLoop();
  println("GAME OVER");   
 }
}
