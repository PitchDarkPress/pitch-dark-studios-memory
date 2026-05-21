PITCH DARK STUDIOS — THE ROOM
SESSION HANDOVER / BUILD RECORD
DATE: 21 MAY 2026
CORE BREAKTHROUGH OF THIS SESSION

This session solved the major technical blocker that had been stopping development:

Three.js + GLB loading on GitHub Pages is now WORKING.

For the first time:

the room renders correctly
GLB models load correctly
lighting works
movement works
camera height works
GitHub Pages deployment works
no more permanent black-screen failure

This is the true foundation build for the room going forward.

REPOSITORY STRUCTURE CONFIRMED

GitHub repo:
pitch-dark-studio-the-room

Files currently in root:

index.html
desk.glb
terminal.glb
lamp.glb
main.js
README.md

GitHub Pages URL:
https://pitchdarkpress.github.io/pitch-dark-studio-the-room/

MAJOR TECHNICAL DISCOVERY
OLD SYSTEM FAILED

The original builds were failing because:

THIS IMPORT SYSTEM BROKE:
import * as THREE from 'three';

GitHub Pages could not resolve module imports correctly.

Result:

endless black screens
renderer never started
GLTFLoader failed
nothing appeared
SOLUTION THAT WORKED

We abandoned the newer ES module import structure and moved to:

<script src="https://cdn.jsdelivr.net/npm/three@0.128.0/build/three.min.js"></script>

<script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/loaders/GLTFLoader.js"></script>

This older Three.js structure works reliably on GitHub Pages.

THIS was the critical breakthrough.

DEVELOPMENT PROCESS FOLLOWED

We rebuilt from absolute basics.

STEP 1 — SIMPLE THREE.JS TEST

Created:

black background
spinning wireframe cube

Confirmed:

renderer works
animation loop works
Three.js works
GitHub Pages works

This eliminated:

browser problems
renderer problems
deployment problems
STEP 2 — GLTF LOADER TEST

Added:

new THREE.GLTFLoader()

Confirmed:

GLTFLoader works
desk.glb loads successfully
no corruption in GLB file

Status output showed:

SCRIPTS LOADED
LOADER OK
DESK LOADED

This confirmed:
THE MODELS WERE NEVER THE REAL PROBLEM.

ROOM BUILD RESTART

After proving loading worked, we rebuilt the room slowly and safely.

CURRENT ROOM STATE

The room now contains:

ENVIRONMENT
large dark room
fog
black ceiling/walls
visible floor plane
LIGHTING

Current lighting setup:

Main spotlight

Position:

light.position.set(0,7,0);

Purpose:

creates desk pool lighting
cinematic overhead focus
Fill light

Soft room illumination added so the room is visible.

Purpose:

prevent pure black environment
allow easier development
atmosphere can be darkened later
Ambient light

Soft ambient added:

new THREE.AmbientLight(0x555555,0.7)

Purpose:

basic visibility
development visibility
prevents crushed blacks
CAMERA

The camera was repeatedly adjusted.

Originally:

far too low
felt like crawling

Final approved height:

camera.position.set(0,3.2,16);

User confirmed:
THIS FEELS CORRECT.

Meaning:

standing adult head height
proper perspective
cinematic framing
MOVEMENT SYSTEM

Current controls:

Arrow keys
Up = move forward
Down = move backward
Left = rotate left
Right = rotate right

Current movement speed:

0.12

Current rotation speed:

0.02
ROOM SCALE

Room intentionally enlarged.

Current room:

80 x 30 x 80

Purpose:

regain “vast dark space” feeling
avoid cramped prototype feel
preserve theatrical emptiness
DESK MODEL

File:

desk.glb

Successfully:

loaded
centered
scaled
shadowed
placed
IMPORTANT DESK ISSUE

The desktop surface texture renders badly.

Symptoms:

fragmented texture
noisy artefacts
corrupted-looking surface

Likely causes:

UV problems
overlapping faces
texture export issues
low-quality source model

Decision:
IGNORE FOR NOW.

Reason:

functionality first
atmosphere still works
can be fixed later
may temporarily add interesting “damaged” feel

Possible future fixes:

replace texture
rebuild top surface
reduce reflectivity
replace material
replace desk model entirely
procedural dark wood material
TERMINAL MODEL

File:

terminal.glb

Successfully:

loaded
scaled
placed
rotated correctly
positioned on desk
TERMINAL ROTATION ISSUE

Initially:

terminal faced wrong direction

We accidentally:

rotated 180°
then rotated wrong 90°

Final correct rotation:

terminal.rotation.y = -Math.PI / 2;

This now faces the camera correctly.

TERMINAL POSITIONING ITERATIONS

We repeatedly adjusted placement.

Problems encountered:

too far back
impossible to use realistically
then too far forward hanging off desk

Final approved position:

terminal.position.set(0,2.05,1.6);

This currently feels believable.

CURRENT VISUAL STATE

The room now successfully conveys:

empty vastness
isolation
theatrical focus
single workstation
abandoned workspace
mood
scale
atmosphere

The project finally feels like:
THE ROOM.

IMPORTANT DEVELOPMENT PHILOSOPHY DECISION

User explicitly requested:

STOP OVERCOMPLICATING.

New build philosophy established:

one change at a time
no giant rewrites
no huge explanations
no advanced architecture yet
prove every step incrementally
maintain stable working base

This dramatically improved progress.

CURRENT STABLE FOUNDATION

The current build now reliably supports:

✅ Room rendering
✅ Camera movement
✅ Fog
✅ Lighting
✅ GLB loading
✅ Desk placement
✅ Terminal placement
✅ GitHub Pages deployment
✅ Shadows
✅ Basic atmosphere

NEXT RECOMMENDED STEPS

Proceed ONLY one object at a time.

Recommended order:

NEXT OBJECT
lamp.glb

Goals:

place on desk
scale correctly
position left or right side
no special lighting yet
AFTER LAMP

Add:

chair
notebook
ashtray
cigarette
glowing tip
smoke
screen glow
blinking cursor
Shakespeare text
IMPORTANT ATMOSPHERE LOCKS

These principles remain locked:

THE ROOM IS:
vast
minimal
theatrical
lonely
cinematic
dark
focused on a single workspace
THE ROOM IS NOT:
cluttered
brightly lit
realistic office space
busy
game-like
CRITICAL SUCCESS OF THIS SESSION

This was arguably the most important technical session so far because:

THE PIPELINE NOW WORKS.

Meaning:

future assets can now be added safely
development can continue incrementally
the black-screen nightmare is effectively solved
the room finally exists as a real navigable space

This session established the true production foundation for:

Pitch Dark Studios — The Room.

---

PITCH DARK STUDIOS — THE ROOM
SESSION HANDOVER / BUILD RECORD
DATE: 21 MAY 2026
CORE BREAKTHROUGH OF THIS SESSION

This session solved the major technical blocker that had been stopping development:

Three.js + GLB loading on GitHub Pages is now WORKING.

For the first time:

the room renders correctly
GLB models load correctly
lighting works
movement works
camera height works
GitHub Pages deployment works
no more permanent black-screen failure

This is the true foundation build for the room going forward.

REPOSITORY STRUCTURE CONFIRMED

GitHub repo:
pitch-dark-studio-the-room

Files currently in root:

index.html
desk.glb
terminal.glb
lamp.glb
main.js
README.md

GitHub Pages URL:
https://pitchdarkpress.github.io/pitch-dark-studio-the-room/

MAJOR TECHNICAL DISCOVERY
OLD SYSTEM FAILED

The original builds were failing because:

THIS IMPORT SYSTEM BROKE:
import * as THREE from 'three';

GitHub Pages could not resolve module imports correctly.

Result:

endless black screens
renderer never started
GLTFLoader failed
nothing appeared
SOLUTION THAT WORKED

We abandoned the newer ES module import structure and moved to:

<script src="https://cdn.jsdelivr.net/npm/three@0.128.0/build/three.min.js"></script>

<script src="https://cdn.jsdelivr.net/npm/three@0.128.0/examples/js/loaders/GLTFLoader.js"></script>

This older Three.js structure works reliably on GitHub Pages.

THIS was the critical breakthrough.

DEVELOPMENT PROCESS FOLLOWED

We rebuilt from absolute basics.

STEP 1 — SIMPLE THREE.JS TEST

Created:

black background
spinning wireframe cube

Confirmed:

renderer works
animation loop works
Three.js works
GitHub Pages works

This eliminated:

browser problems
renderer problems
deployment problems
STEP 2 — GLTF LOADER TEST

Added:

new THREE.GLTFLoader()

Confirmed:

GLTFLoader works
desk.glb loads successfully
no corruption in GLB file

Status output showed:

SCRIPTS LOADED
LOADER OK
DESK LOADED

This confirmed:
THE MODELS WERE NEVER THE REAL PROBLEM.

ROOM BUILD RESTART

After proving loading worked, we rebuilt the room slowly and safely.

CURRENT ROOM STATE

The room now contains:

ENVIRONMENT
large dark room
fog
black ceiling/walls
visible floor plane
LIGHTING

Current lighting setup:

Main spotlight

Position:

light.position.set(0,7,0);

Purpose:

creates desk pool lighting
cinematic overhead focus
Fill light

Soft room illumination added so the room is visible.

Purpose:

prevent pure black environment
allow easier development
atmosphere can be darkened later
Ambient light

Soft ambient added:

new THREE.AmbientLight(0x555555,0.7)

Purpose:

basic visibility
development visibility
prevents crushed blacks
CAMERA

The camera was repeatedly adjusted.

Originally:

far too low
felt like crawling

Final approved height:

camera.position.set(0,3.2,16);

User confirmed:
THIS FEELS CORRECT.

Meaning:

standing adult head height
proper perspective
cinematic framing
MOVEMENT SYSTEM

Current controls:

Arrow keys
Up = move forward
Down = move backward
Left = rotate left
Right = rotate right

Current movement speed:

0.12

Current rotation speed:

0.02
ROOM SCALE

Room intentionally enlarged.

Current room:

80 x 30 x 80

Purpose:

regain “vast dark space” feeling
avoid cramped prototype feel
preserve theatrical emptiness
DESK MODEL

File:

desk.glb

Successfully:

loaded
centered
scaled
shadowed
placed
IMPORTANT DESK ISSUE

The desktop surface texture renders badly.

Symptoms:

fragmented texture
noisy artefacts
corrupted-looking surface

Likely causes:

UV problems
overlapping faces
texture export issues
low-quality source model

Decision:
IGNORE FOR NOW.

Reason:

functionality first
atmosphere still works
can be fixed later
may temporarily add interesting “damaged” feel

Possible future fixes:

replace texture
rebuild top surface
reduce reflectivity
replace material
replace desk model entirely
procedural dark wood material
TERMINAL MODEL

File:

terminal.glb

Successfully:

loaded
scaled
placed
rotated correctly
positioned on desk
TERMINAL ROTATION ISSUE

Initially:

terminal faced wrong direction

We accidentally:

rotated 180°
then rotated wrong 90°

Final correct rotation:

terminal.rotation.y = -Math.PI / 2;

This now faces the camera correctly.

TERMINAL POSITIONING ITERATIONS

We repeatedly adjusted placement.

Problems encountered:

too far back
impossible to use realistically
then too far forward hanging off desk

Final approved position:

terminal.position.set(0,2.05,1.6);

This currently feels believable.

CURRENT VISUAL STATE

The room now successfully conveys:

empty vastness
isolation
theatrical focus
single workstation
abandoned workspace
mood
scale
atmosphere

The project finally feels like:
THE ROOM.

IMPORTANT DEVELOPMENT PHILOSOPHY DECISION

User explicitly requested:

STOP OVERCOMPLICATING.

New build philosophy established:

one change at a time
no giant rewrites
no huge explanations
no advanced architecture yet
prove every step incrementally
maintain stable working base

This dramatically improved progress.

CURRENT STABLE FOUNDATION

The current build now reliably supports:

✅ Room rendering
✅ Camera movement
✅ Fog
✅ Lighting
✅ GLB loading
✅ Desk placement
✅ Terminal placement
✅ GitHub Pages deployment
✅ Shadows
✅ Basic atmosphere

NEXT RECOMMENDED STEPS

Proceed ONLY one object at a time.

Recommended order:

NEXT OBJECT
lamp.glb

Goals:

place on desk
scale correctly
position left or right side
no special lighting yet
AFTER LAMP

Add:

chair
notebook
ashtray
cigarette
glowing tip
smoke
screen glow
blinking cursor
Shakespeare text
IMPORTANT ATMOSPHERE LOCKS

These principles remain locked:

THE ROOM IS:
vast
minimal
theatrical
lonely
cinematic
dark
focused on a single workspace
THE ROOM IS NOT:
cluttered
brightly lit
realistic office space
busy
game-like
CRITICAL SUCCESS OF THIS SESSION

This was arguably the most important technical session so far because:

THE PIPELINE NOW WORKS.

Meaning:

future assets can now be added safely
development can continue incrementally
the black-screen nightmare is effectively solved
the room finally exists as a real navigable space

This session established the true production foundation for:

Pitch Dark Studios — The Room.