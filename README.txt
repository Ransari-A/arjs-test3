AR.js + A-Frame — Super Simple Starter (No Coding Experience Needed)
=====================================================================

What you have:
- `marker.html`  → uses a printed marker (HIRO) to show a 3D box.
- `image.html`   → recognizes a photo (T‑Rex) and shows a 3D model on it.
- `geo.html`     → puts AR text at GPS coordinates (location‑based).
- `index.html`   → a menu page that links to the three demos.

How to run (fastest way):
1) Put these files on a simple web server (HTTPS is required on phones for camera/GPS).
   Easy options:
   - VS Code + Live Server extension (right‑click → “Open with Live Server”)
   - Python: open a terminal in this folder and run:  python -m http.server 8000
   - GitHub Pages or Netlify (just drag‑and‑drop the folder).

2) Open the link on your phone (Safari/Chrome). Allow camera & location permissions.

Demo 1 — Marker (marker.html)
-----------------------------
- Print the HIRO marker (black-and-white square): https://raw.githubusercontent.com/AR-js-org/AR.js/master/data/images/hiro.png
- Point your phone camera at the printed marker. A rotating blue cube appears.
- Try moving/tilting the marker — the cube sticks to it.

Demo 2 — Image Tracking (image.html)
------------------------------------
- Show this image to your camera: https://raw.githubusercontent.com/AR-js-org/AR.js/master/aframe/examples/image-tracking/nft/trex/trex-image-big.jpeg
- When the camera “recognizes” the picture, the T‑Rex 3D model shows up on top.
- Tip: this demo loads files from AR.js’s servers. Use HTTPS and a server to avoid CORS issues.

Demo 3 — Location (geo.html)
----------------------------
- The demo places text at a fixed GPS point (near Duke University Chapel).
- You can change the coordinates inside `geo.html` (look for gps-entity-place).
- Make sure GPS is ON and you’re outside with a clear sky if it doesn’t appear.

Quick mental model (what’s going on)
------------------------------------
- A‑Frame draws 3D graphics in your browser.
- AR.js turns your live camera into “AR mode”:
  • Marker tracking: sticks 3D to a known pattern (HIRO).  
  • Image tracking: sticks 3D to a real photo (T‑Rex).  
  • Location based: sticks 3D to GPS coordinates.
- You just write simple HTML tags; AR.js does the hard math.

Common fixes
------------
- Must use HTTPS (or localhost) for camera/GPS on phones.
- If the camera stays black, refresh and accept camera permission.
- If Image Tracking doesn’t work, check you’re serving over HTTPS and the URL isn’t blocked (CORS).
- On iOS, also allow “Motion & Orientation” in Safari settings for some AR features.

Next steps
----------
- Replace the 3D box with your model:
  <a-entity gltf-model="path/to/yourModel.glb" scale="1 1 1"></a-entity>
- For your own Image Tracking, read AR.js docs on creating NFT descriptors for your image.
- For trails/outdoor pieces, duplicate geo.html and add more <a-text> or <a-entity> lines with different GPS points.
