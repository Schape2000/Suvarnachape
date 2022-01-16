/////sketch.js/////
let video;
let label = "Checking!!!";
let classifier;
let modelURL = 'https://teachablemachine.withgoogle.com/models/iOaDdplJR/';

// STEP 1: Load the model!
function preload() {
  classifier = ml5.imageClassifier(modelURL + 'model.json');
}

function setup() {
  createCanvas(500, 520);
  // Create the video
  video = createCapture(VIDEO);
  video.hide();

  // STEP 2: Start classifying
  classifyVideo();
}
// STEP 2 classify the videeo!
function classifyVideo() {
  classifier.classify(video, gotResults);
}

function draw() {
  background(0);

  
  image(video, 0, 0);

  
  textSize(32);
  textAlign(CENTER, CENTER);
  fill(255);
  text(label, width / 2, height - 16);

  // Pick an emoji, the "default" is train
  let emoji = "⌚";
  if (label == "Good Tomato") {
    emoji = "✔";
  } else if (label == "Damage Tomato") {
    emoji = "❌";
  } else if (label == "Good Onion") {
    emoji = "✔";
  }else if (label == "Damage Onion") {
    emoji = "❌";
  }

  // Drawing the emoji
  textSize(50);
  text(emoji, width -30 , height - 50 );
}
// STEP 3: Get the classification!
function gotResults(error, results) {
  
  if (error) {
    console.error(error);
    return;
  }
  // Storing the label and classifying again!
  label = results[0].label;
  classifyVideo();
}

///////for Ml5////
        <script src="https://unpkg.com/ml5@0.4.2/dist/ml5.min.js"></script>
