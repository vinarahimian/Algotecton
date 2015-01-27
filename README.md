
float R = 0;
float B = 0;
float G =0;

float R1=255;
float G1= 255;
float B1=0;

float R2 = 123;
float G2 = 15;
float B2 = 255;
int changeSpeed = 100;

float dR = (R2-R1) / changeSpeed; 
float dG =  (G2-G1) / changeSpeed; 
float dB = (B2-B1) / changeSpeed; 

float R3 = R1;
float G3 = G1;
float B3 = B1; 

void setup () {
  size (700, 400);
  smooth ();
}


void draw () {

  R = map(mouseX, 0, 700, 0, 255);
  B = map(mouseY, 0, 400, 0, 255);
  G = map(mouseY, 0, 400, 0, 255);
  //G = random ( 0, 255); 
  if (mousePressed) { 
    // in vase range zarde poshte

    if ( abs( R3- R2) > 10) {
      R3 = R3 + dR;
    }
    if ( abs( G3- G2) > 10) 
    {
      G3 = G3 + dG;
    }
    if ( abs( B3- B2) > 10 ) 
    {
      B3 = B3 + dB;
    }


    fill (R3, G3, B3, 20);
    rectMode (CORNER);
    rect (0, 0, width, height);

    // in vase range ranginkamunie mostatilast
    fill ( mouseX, G, mouseY);
    strokeWeight (0.5);
    rectMode (CENTER);
    rect ( mouseX, mouseY, mouseX+ 5, mouseY+20);
    println(R3);
  } else {

    fill (R2, G2, B2);
    rectMode (CORNER);
    rect (0, 0, 700, 400);

    R3 = R1;
    G3 = G1;
    B3 = B1;
  }
  //println(frameCount);
}
