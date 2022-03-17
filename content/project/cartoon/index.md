---
title: Cartoon Face Generator
date: 2022-01-01
summary: Write about your project here...
tags:
  - CV
external_link: http://github.com
---
# Lilac chaser

Look at [this](https://en.wikipedia.org/wiki/Lilac_chaser) introductory reference.

{{< details title="p5-instance-div markdown" open=false >}}
```js
{{</* p5-instance-div id="pacman" >}}
  // Adapted from [this](https://github.com/VisualComputing/Cognitive/blob/gh-pages/sketches/lilacChaser.js)
  p5.jump = 0;
  p5.count = 0;

  p5.setup = function() {
    p5.createCanvas(400, 400);
    p5.frameRate(7);
  };

  p5.drawBlurCircles = function(x, y, r) {
    p5.push();
    p5.noStroke();
    let opc = 0.4;
    let step = 3.0/r;

    for (let i = r; i > 0; i-=1.5) {
      if (opc < 5) {
        opc += step;
        p5.fill(255, 20, 180, opc);
      }
      p5.ellipse(x, y, i, i);
    }
    p5.pop();
  };

  p5.draw = function() {
    p5.background(200);
    let numCircles = 12;
    let stepAngle = 360.0/numCircles;
    p5.push();
    p5.translate(p5.width/2.0, p5.height/2.0);
    for (let i = 0; i < 360; i = i + stepAngle) {
      if (i != p5.jump) {
        p5.push();
        p5.rotate(p5.radians(i));
        p5.drawBlurCircles(120, 0, 60);
        p5.pop();
      }
    }
    if( !p5.mouseIsPressed ) {
      p5.jump = (p5.jump + stepAngle)%360;
    }
    p5.push();
    p5.strokeWeight(1.5);
    p5.line(-7, 0, 7, 0);
    p5.line(0, -7, 0, 7);
    p5.pop();
    p5.pop();
  }
{{< /p5-instance-div */>}}
```
{{< hint warning >}}
Note that `p5` should be the name to be used for the sketch object variable.
{{< /hint >}}
{{< /details >}}

{{< p5-instance-div id="pacman" >}}
  p5.jump = 0;
  p5.count = 0;

  p5.setup = function() {
    p5.createCanvas(380, 380);
    p5.frameRate(7);
  };

  p5.drawBlurCircles = function(x, y, r) {
    p5.push();
    p5.noStroke();
    let opc = 0.4;
    let step = 3.0/r;

    for (let i = r; i > 0; i-=1.5) {
      if (opc < 5) {
        opc += step;
        p5.fill(255, 20, 180, opc);
      }
      p5.ellipse(x, y, i, i);
    }
    p5.pop();
  };

  p5.draw = function() {
    p5.background(200);
    let numCircles = 12;
    let stepAngle = 360.0/numCircles;
    p5.push();
    p5.translate(p5.width/2.0, p5.height/2.0);
    for (let i = 0; i < 360; i = i + stepAngle) {
      if (i != p5.jump) {
        p5.push();
        p5.rotate(p5.radians(i));
        p5.drawBlurCircles(120, 0, 60);
        p5.pop();
      }
    }
    if( !p5.mouseIsPressed ) {
      p5.jump = (p5.jump + stepAngle)%360;
    }
    p5.push();
    p5.strokeWeight(1.5);
    p5.line(-7, 0, 7, 0);
    p5.line(0, -7, 0, 7);
    p5.pop();
    p5.pop();
  }
{{< /p5-instance-div >}}