<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Solar System Explorer - 3D Space Game</title>
<style>
* {
margin: 0;
padding: 0;
box-sizing: border-box;
}

body {
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
background: radial-gradient(ellipse at center, #1a1a2e 0%, #16213e 50%, #0f0f23 100%);
overflow: hidden;
color: white;
}

#gameContainer {
position: relative;
width: 100vw;
height: 100vh;
}

#canvas {
display: block;
cursor: grab;
}

#canvas:active {
cursor: grabbing;
}

.ui-panel {
position: absolute;
background: rgba(0, 20, 40, 0.9);
border: 1px solid rgba(100, 200, 255, 0.3);
border-radius: 10px;
padding: 15px;
backdrop-filter: blur(10px);
box-shadow: 0 4px 20px rgba(0, 100, 200, 0.2);
}

#controlPanel {
top: 20px;
left: 20px;
width: 280px;
}

#infoPanel {
top: 20px;
right: 20px;
width: 300px;
max-height: 70vh;
overflow-y: auto;
}

#bottomPanel {
bottom: 20px;
left: 50%;
transform: translateX(-50%);
display: flex;
gap: 15px;
align-items: center;
}

.control-group {
margin-bottom: 15px;
}

.control-group h3 {
color: #64b5f6;
margin-bottom: 8px;
font-size: 14px;
text-transform: uppercase;
letter-spacing: 1px;
}

.control-row {
display: flex;
gap: 10px;
margin-bottom: 8px;
align-items: center;
}

button {
background: linear-gradient(135deg, #1976d2, #1565c0);
border: none;
color: white;
padding: 8px 12px;
border-radius: 6px;
cursor: pointer;
font-size: 12px;
transition: all 0.3s ease;
border: 1px solid rgba(100, 200, 255, 0.3);
}

button:hover {
background: linear-gradient(135deg, #2196f3, #1976d2);
transform: translateY(-1px);
box-shadow: 0 4px 12px rgba(33, 150, 243, 0.3);
}

button:active {
transform: translateY(0);
}

button.active {
background: linear-gradient(135deg, #4caf50, #388e3c);
}

input[type="range"] {
width: 100%;
margin: 5px 0;
}

.speed-display {
font-size: 11px;
color: #90caf9;
text-align: center;
}

.celestial-info {
margin-bottom: 15px;
padding: 10px;
background: rgba(0, 50, 100, 0.3);
border-radius: 8px;
border-left: 3px solid #64b5f6;
}

.celestial-info h4 {
color: #81c784;
margin-bottom: 5px;
}

.info-item {
display: flex;
justify-content: space-between;
margin: 3px 0;
font-size: 12px;
}

.info-label {
color: #b0bec5;
}

.info-value {
color: #e1f5fe;
font-weight: bold;
}

.physics-panel {
margin-top: 15px;
padding: 10px;
background: rgba(100, 50, 0, 0.2);
border-radius: 8px;
border-left: 3px solid #ff9800;
}

.physics-panel h4 {
color: #ffb74d;
margin-bottom: 8px;
}

.measurement-tool {
background: rgba(50, 100, 50, 0.3);
border-left: 3px solid #4caf50;
padding: 8px;
margin: 5px 0;
border-radius: 5px;
}

.stars {
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
pointer-events: none;
}

.star {
position: absolute;
background: white;
border-radius: 50%;
animation: twinkle 3s infinite;
}

@keyframes twinkle {
0%, 100% { opacity: 0.3; }
50% { opacity: 1; }
}

.orbit-trail {
position: absolute;
border: 1px dashed rgba(100, 200, 255, 0.3);
border-radius: 50%;
pointer-events: none;
}

#instructions {
position: absolute;
bottom: 20px;
left: 20px;
font-size: 11px;
color: #90caf9;
background: rgba(0, 20, 40, 0.8);
padding: 10px;
border-radius: 5px;
max-width: 250px;
}
</style>
</head>
<body>
<div id="gameContainer">
<!-- Starfield background -->
<div class="stars" id="starfield"></div>

<!-- Main 3D Canvas -->
<canvas id="canvas"></canvas>

<!-- Control Panel -->
<div id="controlPanel" class="ui-panel">
<div class="control-group">
<h3>🚀 Navigation</h3>
<div class="control-row">
<button onclick="focusOnBody('sun')">☀️ Sun</button>
<button onclick="focusOnBody('earth')">🌍 Earth</button>
<button onclick="focusOnBody('mars')">🔴 Mars</button>
</div>
<div class="control-row">
<button onclick="resetView()">🏠 Reset View</button>
<button onclick="toggleOrbits()" id="orbitBtn">🔄 Orbits</button>
</div>
</div>

<div class="control-group">
<h3>⏱️ Time Control</h3>
<div class="control-row">
<button onclick="pauseTime()" id="pauseBtn">⏸️ Pause</button>
<button onclick="resetTime()">⏮️ Reset</button>
</div>
<input type="range" id="speedSlider" min="0" max="10" value="1" step="0.1" oninput="updateSpeed(this.value)">
<div class="speed-display" id="speedDisplay">Speed: 1x</div>
</div>

<div class="control-group">
<h3>📏 Tools</h3>
<div class="control-row">
<button onclick="toggleMeasurement()" id="measureBtn">📐 Measure</button>
<button onclick="showPhysics()" id="physicsBtn">⚡ Physics</button>
</div>
</div>
</div>

<!-- Information Panel -->
<div id="infoPanel" class="ui-panel">
<div id="selectedBodyInfo">
<h3 style="color: #64b5f6; margin-bottom: 10px;">🌌 Solar System Explorer</h3>
<p style="font-size: 12px; color: #b0bec5; margin-bottom: 15px;">
Click and drag to rotate view. Use mouse wheel to zoom. Click on celestial bodies to learn more!
</p>
</div>

<div id="physicsInfo" class="physics-panel" style="display: none;">
<h4>⚡ Orbital Mechanics</h4>
<div class="info-item">
<span class="info-label">Kepler's 1st Law:</span>
<span class="info-value">Elliptical Orbits</span>
</div>
<div class="info-item">
<span class="info-label">Kepler's 2nd Law:</span>
<span class="info-value">Equal Areas</span>
</div>
<div class="info-item">
<span class="info-label">Kepler's 3rd Law:</span>
<span class="info-value">Period² ∝ Distance³</span>
</div>
<p style="font-size: 11px; margin-top: 8px; color: #ffcc80;">
Objects closer to the Sun orbit faster. Earth takes 365 days, Mars takes 687 days!
</p>
</div>

<div id="measurementInfo" class="measurement-tool" style="display: none;">
<h4>📏 Distance Measurement</h4>
<div id="distanceReadout">Click two objects to measure distance</div>
</div>
</div>

<!-- Bottom Status Panel -->
<div id="bottomPanel" class="ui-panel">
<div style="font-size: 12px;">
<span style="color: #64b5f6;">Date:</span>
<span id="currentDate">Jan 1, 2024</span>
</div>
<div style="font-size: 12px;">
<span style="color: #64b5f6;">View:</span>
<span id="viewMode">Free Camera</span>
</div>
</div>

<!-- Instructions -->
<div id="instructions">
<strong>Controls:</strong><br>
• Drag to rotate view<br>
• Scroll to zoom<br>
• Click objects for info<br>
• Use time controls to see orbital motion
</div>
</div>

<script>
// Game state
let gameState = {
canvas: null,
ctx: null,
camera: { x: 0, y: 0, zoom: 1, rotation: 0 },
time: 0,
timeSpeed: 1,
paused: false,
showOrbits: true,
showPhysics: false,
measurementMode: false,
measurementPoints: [],
selectedBody: null,
mouse: { x: 0, y: 0, down: false, lastX: 0, lastY: 0 }
};

// Celestial bodies data (scaled for visualization)
const celestialBodies = {
sun: {
name: "Sun",
x: 0, y: 0, z: 0,
radius: 30,
color: "#FDB813",
glowColor: "#FFE082",
mass: "1.989 × 10³⁰ kg",
diameter: "1.39 million km",
temperature: "5,778 K",
type: "G-type Star",
facts: "The Sun contains 99.86% of the Solar System's mass and generates energy through nuclear fusion."
},
earth: {
name: "Earth",
x: 0, y: 0, z: 0,
radius: 8,
color: "#6B93D6",
glowColor: "#81C784",
orbitRadius: 150,
orbitSpeed: 0.02,
orbitOffset: 0,
mass: "5.972 × 10²⁴ kg",
diameter: "12,742 km",
distance: "149.6 million km",
period: "365.25 days",
facts: "Earth is the only known planet with life, protected by its magnetic field and atmosphere.",
moon: {
name: "Moon",
radius: 2,
color: "#C0C0C0",
orbitRadius: 20,
orbitSpeed: 0.1,
mass: "7.342 × 10²² kg",
diameter: "3,474 km",
distance: "384,400 km from Earth"
}
},
mars: {
name: "Mars",
x: 0, y: 0, z: 0,
radius: 6,
color: "#CD5C5C",
glowColor: "#FF8A65",
orbitRadius: 230,
orbitSpeed: 0.011,
orbitOffset: Math.PI / 3,
mass: "6.39 × 10²³ kg",
diameter: "6,779 km",
distance: "227.9 million km",
period: "687 days",
facts: "Mars has the largest volcano in the solar system (Olympus Mons) and evidence of ancient water flows."
}
};

// Initialize the game
function initGame() {
gameState.canvas = document.getElementById('canvas');
gameState.ctx = gameState.canvas.getContext('2d');

resizeCanvas();
createStarfield();
setupEventListeners();

// Start game loop
gameLoop();
}

function resizeCanvas() {
gameState.canvas.width = window.innerWidth;
gameState.canvas.height = window.innerHeight;
}

function createStarfield() {
const starfield = document.getElementById('starfield');
for (let i = 0; i < 200; i++) {
const star = document.createElement('div');
star.className = 'star';
star.style.left = Math.random() * 100 + '%';
star.style.top = Math.random() * 100 + '%';
star.style.width = star.style.height = (Math.random() * 2 + 1) + 'px';
star.style.animationDelay = Math.random() * 3 + 's';
starfield.appendChild(star);
}
}

function setupEventListeners() {
const canvas = gameState.canvas;

// Mouse controls
canvas.addEventListener('mousedown', handleMouseDown);
canvas.addEventListener('mousemove', handleMouseMove);
canvas.addEventListener('mouseup', handleMouseUp);
canvas.addEventListener('wheel', handleWheel);
canvas.addEventListener('click', handleClick);

// Window resize
window.addEventListener('resize', resizeCanvas);
}

function handleMouseDown(e) {
gameState.mouse.down = true;
gameState.mouse.lastX = e.clientX;
gameState.mouse.lastY = e.clientY;
}

function handleMouseMove(e) {
gameState.mouse.x = e.clientX;
gameState.mouse.y = e.clientY;

if (gameState.mouse.down) {
const deltaX = e.clientX - gameState.mouse.lastX;
const deltaY = e.clientY - gameState.mouse.lastY;

gameState.camera.rotation += deltaX * 0.01;
gameState.camera.y += deltaY * 0.5;

gameState.mouse.lastX = e.clientX;
gameState.mouse.lastY = e.clientY;
}
}

function handleMouseUp(e) {
gameState.mouse.down = false;
}

function handleWheel(e) {
e.preventDefault();
const zoomFactor = e.deltaY > 0 ? 0.9 : 1.1;
gameState.camera.zoom = Math.max(0.1, Math.min(5, gameState.camera.zoom * zoomFactor));
}

function handleClick(e) {
const rect = gameState.canvas.getBoundingClientRect();
const clickX = e.clientX - rect.left;
const clickY = e.clientY - rect.top;

// Check if clicked on a celestial body
const clickedBody = getClickedBody(clickX, clickY);
if (clickedBody) {
selectBody(clickedBody);

if (gameState.measurementMode) {
addMeasurementPoint(clickedBody);
}
}
}

function getClickedBody(x, y) {
const centerX = gameState.canvas.width / 2;
const centerY = gameState.canvas.height / 2;

for (const [key, body] of Object.entries(celestialBodies)) {
if (key === 'sun') {
const distance = Math.sqrt((x - centerX) ** 2 + (y - centerY) ** 2);
if (distance <= body.radius * gameState.camera.zoom) {
return key;
}
} else {
updateBodyPosition(body);
const screenX = centerX + (body.x * gameState.camera.zoom);
const screenY = centerY + (body.y * gameState.camera.zoom);
const distance = Math.sqrt((x - screenX) ** 2 + (y - screenY) ** 2);

if (distance <= body.radius * gameState.camera.zoom) {
return key;
}

// Check moon
if (body.moon) {
const moonAngle = gameState.time * body.moon.orbitSpeed;
const moonX = screenX + Math.cos(moonAngle) * body.moon.orbitRadius * gameState.camera.zoom;
const moonY = screenY + Math.sin(moonAngle) * body.moon.orbitRadius * gameState.camera.zoom;
const moonDistance = Math.sqrt((x - moonX) ** 2 + (y - moonY) ** 2);

if (moonDistance <= body.moon.radius * gameState.camera.zoom) {
return key + '_moon';
}
}
}
}
return null;
}

function updateBodyPosition(body) {
if (body.orbitRadius) {
const angle = gameState.time * body.orbitSpeed + body.orbitOffset;
body.x = Math.cos(angle + gameState.camera.rotation) * body.orbitRadius;
body.y = Math.sin(angle + gameState.camera.rotation) * body.orbitRadius;
}
}

function gameLoop() {
if (!gameState.paused) {
gameState.time += gameState.timeSpeed * 0.1;
updateDate();
}

render();
requestAnimationFrame(gameLoop);
}

function render() {
const ctx = gameState.ctx;
const canvas = gameState.canvas;

// Clear canvas
ctx.fillStyle = 'rgba(10, 10, 30, 0.1)';
ctx.fillRect(0, 0, canvas.width, canvas.height);

const centerX = canvas.width / 2 + gameState.camera.x;
const centerY = canvas.height / 2 + gameState.camera.y;

// Draw orbit paths
if (gameState.showOrbits) {
drawOrbits(ctx, centerX, centerY);
}

// Draw celestial bodies
drawCelestialBodies(ctx, centerX, centerY);

// Draw measurement lines
if (gameState.measurementMode && gameState.measurementPoints.length > 0) {
drawMeasurementLines(ctx, centerX, centerY);
}
}

function drawOrbits(ctx, centerX, centerY) {
ctx.strokeStyle = 'rgba(100, 200, 255, 0.2)';
ctx.lineWidth = 1;
ctx.setLineDash([5, 5]);

for (const [key, body] of Object.entries(celestialBodies)) {
if (body.orbitRadius) {
ctx.beginPath();
ctx.arc(centerX, centerY, body.orbitRadius * gameState.camera.zoom, 0, Math.PI * 2);
ctx.stroke();
}
}

ctx.setLineDash([]);
}

function drawCelestialBodies(ctx, centerX, centerY) {
// Draw Sun
drawBody(ctx, celestialBodies.sun, centerX, centerY, true);

// Draw planets
for (const [key, body] of Object.entries(celestialBodies)) {
if (key !== 'sun') {
updateBodyPosition(body);
const x = centerX + body.x * gameState.camera.zoom;
const y = centerY + body.y * gameState.camera.zoom;

drawBody(ctx, body, x, y, false);

// Draw moon
if (body.moon) {
const moonAngle = gameState.time * body.moon.orbitSpeed;
const moonX = x + Math.cos(moonAngle) * body.moon.orbitRadius * gameState.camera.zoom;
const moonY = y + Math.sin(moonAngle) * body.moon.orbitRadius * gameState.camera.zoom;

drawBody(ctx, body.moon, moonX, moonY, false);

// Draw moon orbit
if (gameState.showOrbits) {
ctx.strokeStyle = 'rgba(200, 200, 200, 0.3)';
ctx.lineWidth = 1;
ctx.beginPath();
ctx.arc(x, y, body.moon.orbitRadius * gameState.camera.zoom, 0, Math.PI * 2);
ctx.stroke();
}
}
}
}
}

function drawBody(ctx, body, x, y, isSun = false) {
const radius = body.radius * gameState.camera.zoom;

// Draw glow effect
if (isSun || body.glowColor) {
const gradient = ctx.createRadialGradient(x, y, 0, x, y, radius * 2);
gradient.addColorStop(0, body.glowColor || body.color);
gradient.addColorStop(1, 'transparent');
ctx.fillStyle = gradient;
ctx.beginPath();
ctx.arc(x, y, radius * 2, 0, Math.PI * 2);
ctx.fill();
}

// Draw main body
ctx.fillStyle = body.color;
ctx.beginPath();
ctx.arc(x, y, radius, 0, Math.PI * 2);
ctx.fill();

// Draw selection highlight
if (gameState.selectedBody === body.name.toLowerCase().replace(' ', '_')) {
ctx.strokeStyle = '#FFD700';
ctx.lineWidth = 3;
ctx.beginPath();
ctx.arc(x, y, radius + 5, 0, Math.PI * 2);
ctx.stroke();
}
}

function drawMeasurementLines(ctx, centerX, centerY) {
if (gameState.measurementPoints.length >= 2) {
ctx.strokeStyle = '#4CAF50';
ctx.lineWidth = 2;
ctx.setLineDash([10, 5]);

for (let i = 0; i < gameState.measurementPoints.length - 1; i++) {
const point1 = getBodyScreenPosition(gameState.measurementPoints[i], centerX, centerY);
const point2 = getBodyScreenPosition(gameState.measurementPoints[i + 1], centerX, centerY);

ctx.beginPath();
ctx.moveTo(point1.x, point1.y);
ctx.lineTo(point2.x, point2.y);
ctx.stroke();
}

ctx.setLineDash([]);
}
}

function getBodyScreenPosition(bodyKey, centerX, centerY) {
if (bodyKey === 'sun') {
return { x: centerX, y: centerY };
}

const body = celestialBodies[bodyKey.replace('_moon', '')];
updateBodyPosition(body);

if (bodyKey.includes('_moon')) {
const moonAngle = gameState.time * body.moon.orbitSpeed;
return {
x: centerX + (body.x + Math.cos(moonAngle) * body.moon.orbitRadius) * gameState.camera.zoom,
y: centerY + (body.y + Math.sin(moonAngle) * body.moon.orbitRadius) * gameState.camera.zoom
};
}

return {
x: centerX + body.x * gameState.camera.zoom,
y: centerY + body.y * gameState.camera.zoom
};
}

// Control functions
function focusOnBody(bodyKey) {
gameState.selectedBody = bodyKey;
selectBody(bodyKey);

if (bodyKey === 'sun') {
gameState.camera.x = 0;
gameState.camera.y = 0;
gameState.camera.zoom = 1;
} else {
const body = celestialBodies[bodyKey];
updateBodyPosition(body);
gameState.camera.x = -body.x * gameState.camera.zoom;
gameState.camera.y = -body.y * gameState.camera.zoom;
}

document.getElementById('viewMode').textContent = `Following ${celestialBodies[bodyKey].name}`;
}

function resetView() {
gameState.camera = { x: 0, y: 0, zoom: 1, rotation: 0 };
gameState.selectedBody = null;
document.getElementById('viewMode').textContent = 'Free Camera';
updateInfoPanel();
}

function toggleOrbits() {
gameState.showOrbits = !gameState.showOrbits;
const btn = document.getElementById('orbitBtn');
btn.classList.toggle('active', gameState.showOrbits);
btn.textContent = gameState.showOrbits ? '🔄 Orbits' : '🔄 Orbits';
}

function pauseTime() {
gameState.paused = !gameState.paused;
const btn = document.getElementById('pauseBtn');
btn.textContent = gameState.paused ? '▶️ Play' : '⏸️ Pause';
btn.classList.toggle('active', gameState.paused);
}

function resetTime() {
gameState.time = 0;
updateDate();
}

function updateSpeed(value) {
gameState.timeSpeed = parseFloat(value);
document.getElementById('speedDisplay').textContent = `Speed: ${value}x`;
}

function toggleMeasurement() {
gameState.measurementMode = !gameState.measurementMode;
const btn = document.getElementById('measureBtn');
btn.classList.toggle('active', gameState.measurementMode);

if (!gameState.measurementMode) {
gameState.measurementPoints = [];
document.getElementById('measurementInfo').style.display = 'none';
} else {
document.getElementById('measurementInfo').style.display = 'block';
}
}

function showPhysics() {
gameState.showPhysics = !gameState.showPhysics;
const btn = document.getElementById('physicsBtn');
btn.classList.toggle('active', gameState.showPhysics);
document.getElementById('physicsInfo').style.display = gameState.showPhysics ? 'block' : 'none';
}

function addMeasurementPoint(bodyKey) {
gameState.measurementPoints.push(bodyKey);

if (gameState.measurementPoints.length >= 2) {
calculateDistance();
}

if (gameState.measurementPoints.length > 2) {
gameState.measurementPoints = gameState.measurementPoints.slice(-2);
}
}

function calculateDistance() {
const point1 = gameState.measurementPoints[0];
const point2 = gameState.measurementPoints[1];

// Get real distances (simplified)
const distances = {
'sun-earth': '149.6 million km',
'earth-mars': '54.6 - 401 million km',
'sun-mars': '227.9 million km',
'earth-earth_moon': '384,400 km'
};

const key1 = `${point1}-${point2}`;
const key2 = `${point2}-${point1}`;

const distance = distances[key1] || distances[key2] || 'Distance varies with orbital position';

document.getElementById('distanceReadout').innerHTML = `
<strong>${celestialBodies[point1.replace('_moon', '')].name}${point1.includes('_moon') ? ' Moon' : ''} ↔
${celestialBodies[point2.replace('_moon', '')].name}${point2.includes('_moon') ? ' Moon' : ''}</strong><br>
Distance: ${distance}
`;
}

function selectBody(bodyKey) {
gameState.selectedBody = bodyKey;
updateInfoPanel();
}

function updateInfoPanel() {
const infoDiv = document.getElementById('selectedBodyInfo');

if (!gameState.selectedBody) {
infoDiv.innerHTML = `
<h3 style="color: #64b5f6; margin-bottom: 10px;">🌌 Solar System Explorer</h3>
<p style="font-size: 12px; color: #b0bec5; margin-bottom: 15px;">
Click and drag to rotate view. Use mouse wheel to zoom. Click on celestial bodies to learn more!
</p>
`;
return;
}

const bodyKey = gameState.selectedBody.replace('_moon', '');
const body = celestialBodies[bodyKey];
const isMoon = gameState.selectedBody.includes('_moon');
const selectedData = isMoon ? body.moon : body;

infoDiv.innerHTML = `
<div class="celestial-info">
<h4>${selectedData.name}</h4>
<div class="info-item">
<span class="info-label">Mass:</span>
<span class="info-value">${selectedData.mass}</span>
</div>
<div class="info-item">
<span class="info-label">Diameter:</span>
<span class="info-value">${selectedData.diameter}</span>
</div>
${selectedData.distance ? `
<div class="info-item">
<span class="info-label">Distance:</span>
<span class="info-value">${selectedData.distance}</span>
</div>` : ''}
${selectedData.period ? `
<div class="info-item">
<span class="info-label">Orbital Period:</span>
<span class="info-value">${selectedData.period}</span>
</div>` : ''}
${selectedData.temperature ? `
<div class="info-item">
<span class="info-label">Temperature:</span>
<span class="info-value">${selectedData.temperature}</span>
</div>` : ''}
${selectedData.type ? `
<div class="info-item">
<span class="info-label">Type:</span>
<span class="info-value">${selectedData.type}</span>
</div>` : ''}
<p style="font-size: 11px; margin-top: 8px; color: #e1f5fe;">
${selectedData.facts}
</p>
</div>
`;
}

function updateDate() {
const startDate = new Date(2024, 0, 1);
const currentDate = new Date(startDate.getTime() + gameState.time * 24 * 60 * 60 * 1000);
document.getElementById('currentDate').textContent = currentDate.toLocaleDateString('en-US', {
month: 'short',
day: 'numeric',
year: 'numeric'
});
}

// Initialize the game when page loads
window.addEventListener('load', initGame);
</script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'96dc3fe68088b5ce',t:'MTc1NDk2MjY2OC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
