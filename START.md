Abre https://www.khanacademy.org/computer-programming/new/pjs y pega el código abajo:

```
noStroke();
background(0,0,0);

var Star = function(color) {
    this.color = color;
    this.x = 0;
    this.y = 0;
    
    this.interna = function(x, y) {
        fill(random(0,255), random(0,255), random(0,255));
        triangle(x-10, y+15, x, y, x+10, y+15);
        triangle(x-10, y+5, x, y+20, x+10, y+5);
    };
    
    this.pintar = function() {
        fill(this.color);
        scale(random(1,2),random(1,2));
        rotate(random(-30,30));
        triangle(this.x-15, this.y+20, this.x, this.y, this.x+15, this.y+20);
        triangle(this.x-15, this.y+7, this.x, this.y+27, this.x+15, this.y+7);
        this.interna(this.x, this.y+3);
    };
    
    this.fiesta = function() {
        this.pintar();
        this.x = random(0, 300);
        this.y = random(0, 300);
    };
};

var estrella = new Star(color(255, 0, 0));
var estrella2 = new Star(color(255, 255, 0));

draw = function() {
    background(0,0,0);
    estrella.fiesta();
    estrella2.fiesta();
};
```
