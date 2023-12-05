<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <script defer src="https://cdnjs.cloudflare.com/ajax/libs/p5.js/1.4.0/p5.js"></script>
  <style>
    body {
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
    }
  </style>
</head>
<body>
  <main aria-live="polite">
    <p id="dynamic-description">A circle will appear when and where you click, its color will be random, and it will resize as you move the mouse up and down.</p>

  <script>
    // Define variables
    let circleX, circleY;
    let bgColor;

    function setup() {
      createCanvas(400, 400);
      // Initialize variables
      circleX = width / 2;
      circleY = height / 2;
      bgColor = color(200, 200, 200);
    }

    function draw() {
      background(bgColor);

      // Draw a circle at the current position
      fill(255, 0, 0);
      ellipse(circleX, circleY, 50, 50);
    }

    function mousePressed() {
      // Change circle color on mouse press
      bgColor = color(random(255), random(255), random(255));

      // Move circle to the mouse position on mouse press
      circleX = mouseX;
      circleY = mouseY;
    }

    function mouseMoved() {
      // Change circle size based on mouse Y position
      let newSize = map(mouseY, 0, height, 10, 100);
      ellipse(circleX, circleY, newSize, newSize);
    }
  </script>

  </main>
</body>
</html>
