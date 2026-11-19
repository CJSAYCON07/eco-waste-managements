<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Barangay Waste Segregation AI Scanner & Guide</title>
  <!-- TensorFlow.js & Teachable Machine Image Library -->
  <script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs@latest/dist/tf.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/@teachablemachine/image@latest/dist/teachablemachine-image.min.js"></script>
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet" />

  <style>
    :root {
      --primary-green: #15803d;
      --primary-dark: #14532d;
      --primary-light: #dcfce7;
      --bg-page: #f8faf9;
      --bg-card: #ffffff;
      --text-main: #1e293b;
      --text-muted: #64748b;
      --border-light: #e2e8f0;

      /* Waste Category Colors (2 Classes) */
      --bio-color: #16a34a;
      --bio-bg: #f0fdf4;

      --nonbio-color: #2563eb;
      --nonbio-bg: #eff6ff;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      background-color: var(--bg-page);
      color: var(--text-main);
      line-height: 1.6;
    }

    header {
      background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary-green) 100%);
      color: #ffffff;
      padding: 2.5rem 1.5rem 3.5rem;
      text-align: center;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      background: rgba(255, 255, 255, 0.16);
      backdrop-filter: blur(6px);
      padding: 0.35rem 0.9rem;
      border-radius: 999px;
      font-size: 0.8rem;
      font-weight: 600;
      letter-spacing: 0.03em;
      text-transform: uppercase;
      margin-bottom: 0.85rem;
    }

    header h1 {
      font-size: clamp(1.65rem, 3.5vw, 2.45rem);
      font-weight: 800;
      letter-spacing: -0.02em;
      max-width: 780px;
      margin: 0 auto 0.65rem;
    }

    header p {
      font-size: 1rem;
      color: #dcfce7;
      max-width: 640px;
      margin: 0 auto;
    }

    .container {
      max-width: 1080px;
      margin: -2rem auto 4rem;
      padding: 0 1.25rem;
    }

    .scanner-card {
      background: var(--bg-card);
      border-radius: 20px;
      box-shadow: 0 12px 32px rgba(20, 83, 45, 0.08);
      border: 1px solid var(--border-light);
      padding: 1.75rem;
      margin-bottom: 3rem;
    }

    .scanner-header {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
      padding-bottom: 1.25rem;
      border-bottom: 1px solid var(--border-light);
      margin-bottom: 1.5rem;
    }

    .scanner-title h2 {
      font-size: 1.3rem;
      font-weight: 700;
      color: var(--primary-dark);
    }

    .scanner-title span {
      font-size: 0.88rem;
      color: var(--text-muted);
    }

    .mode-controls {
      display: flex;
      gap: 0.65rem;
      flex-wrap: wrap;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 0.5rem;
      padding: 0.65rem 1.15rem;
      border-radius: 10px;
      font-size: 0.9rem;
      font-weight: 600;
      cursor: pointer;
      border: none;
      transition: all 0.2s ease;
    }

    .btn-primary {
      background-color: var(--primary-green);
      color: #ffffff;
    }

    .btn-primary:hover {
      background-color: var(--primary-dark);
    }

    .btn-outline {
      background-color: #ffffff;
      color: var(--primary-green);
      border: 1.5px solid var(--primary-green);
    }

    .btn-outline:hover {
      background-color: var(--primary-light);
    }

    .btn-danger {
      background-color: #fee2e2;
      color: #b91c1c;
    }

    .scanner-grid {
      display: grid;
      grid-template-columns: 1fr 1.15fr;
      gap: 2rem;
      align-items: start;
    }

    @media (max-width: 820px) {
      .scanner-grid {
        grid-template-columns: 1fr;
      }
    }

    .viewport-wrapper {
      background: #f1f5f9;
      border: 2px dashed #cbd5e1;
      border-radius: 16px;
      min-height: 310px;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      position: relative;
      overflow: hidden;
      text-align: center;
      padding: 1rem;
    }

    .viewport-wrapper.active {
      border-style: solid;
      border-color: var(--primary-green);
      background: #0f172a;
    }

    #webcam-container canvas,
    #image-preview {
      max-width: 100%;
      max-height: 310px;
      border-radius: 12px;
      display: block;
      margin: 0 auto;
    }

    .placeholder-state {
      color: var(--text-muted);
      max-width: 270px;
    }

    .placeholder-state svg {
      width: 48px;
      height: 48px;
      color: var(--primary-green);
      margin-bottom: 0.75rem;
    }

    .model-status {
      font-size: 0.82rem;
      font-weight: 600;
      margin-top: 0.75rem;
      padding: 0.35rem 0.75rem;
      border-radius: 999px;
      background: var(--primary-light);
      color: var(--primary-dark);
      display: inline-block;
    }

    .results-panel {
      display: flex;
      flex-direction: column;
      gap: 1.25rem;
    }

    .instruction-box {
      padding: 1.25rem;
      border-radius: 14px;
      border-left: 6px solid var(--primary-green);
      background-color: var(--primary-light);
      transition: all 0.3s ease;
    }

    .instruction-box.bio {
      background-color: var(--bio-bg);
      border-color: var(--bio-color);
    }
    .instruction-box.nonbio {
      background-color: var(--nonbio-bg);
      border-color: var(--nonbio-color);
    }

    .instruction-label {
      font-size: 0.78rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.05em;
      color: var(--text-muted);
      margin-bottom: 0.25rem;
    }

    .instruction-bin {
      font-size: 1.25rem;
      font-weight: 800;
      color: var(--text-main);
      margin-bottom: 0.35rem;
    }

    .instruction-text {
      font-size: 0.92rem;
      color: #334155;
    }

    .confidence-list {
      display: flex;
      flex-direction: column;
      gap: 1.1rem;
    }

    .confidence-item {
      display: flex;
      flex-direction: column;
      gap: 0.35rem;
    }

    .confidence-meta {
      display: flex;
      justify-content: space-between;
      font-size: 0.9rem;
      font-weight: 600;
    }

    .bar-track {
      width: 100%;
      height: 14px;
      background-color: #e2e8f0;
      border-radius: 999px;
      overflow: hidden;
    }

    .bar-fill {
      height: 100%;
      width: 0%;
      border-radius: 999px;
      transition: width 0.25s ease;
    }

    .fill-bio { background-color: var(--bio-color); }
    .fill-nonbio { background-color: var(--nonbio-color); }

    .edu-section {
      margin-bottom: 3rem;
    }

    .section-heading {
      display: flex;
      align-items: center;
      gap: 0.75rem;
      margin-bottom: 1.25rem;
    }

    .section-num {
      width: 34px;
      height: 34px;
      border-radius: 10px;
      background: var(--primary-green);
      color: #ffffff;
      font-weight: 700;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 0.95rem;
      flex-shrink: 0;
    }

    .section-heading h2 {
      font-size: 1.45rem;
      font-weight: 700;
      color: var(--primary-dark);
    }

    .card-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem;
    }

    .info-card {
      background: var(--bg-card);
      border-radius: 16px;
      padding: 1.5rem;
      border: 1px solid var(--border-light);
      box-shadow: 0 4px 14px rgba(0, 0, 0, 0.03);
    }

    .info-card h3 {
      font-size: 1.15rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    .info-card p, .info-card li {
      font-size: 0.92rem;
      color: var(--text-muted);
    }

    .info-card ul {
      padding-left: 1.15rem;
      margin-top: 0.5rem;
      display: flex;
      flex-direction: column;
      gap: 0.35rem;
    }

    .cat-bio { border-top: 4px solid var(--bio-color); }
    .cat-nonbio { border-top: 4px solid var(--nonbio-color); }

    .bin-tag {
      display: inline-block;
      font-size: 0.75rem;
      font-weight: 700;
      padding: 0.2rem 0.6rem;
      border-radius: 6px;
      margin-bottom: 0.6rem;
    }

    .tag-bio { background: var(--bio-bg); color: var(--bio-color); }
    .tag-nonbio { background: var(--nonbio-bg); color: var(--nonbio-color); }

    .table-wrapper {
      background: var(--bg-card);
      border-radius: 16px;
      border: 1px solid var(--border-light);
      overflow-x: auto;
      box-shadow: 0 4px 14px rgba(0, 0, 0, 0.03);
    }

    table {
      width: 100%;
      border-collapse: collapse;
      text-align: left;
      font-size: 0.92rem;
    }

    th {
      background: var(--primary-light);
      color: var(--primary-dark);
      font-weight: 700;
      padding: 0.95rem 1.25rem;
    }

    td {
      padding: 0.95rem 1.25rem;
      border-top: 1px solid var(--border-light);
    }

    .impact-banner {
      margin-top: 1.25rem;
      background: linear-gradient(135deg, #ecfdf5 0%, #d1fae5 100%);
      border: 1px solid #a7f3d0;
      border-radius: 14px;
      padding: 1.25rem 1.5rem;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
    }

    .impact-stat {
      text-align: center;
      flex: 1;
      min-width: 150px;
    }

    .impact-stat strong {
      display: block;
      font-size: 1.55rem;
      font-weight: 800;
      color: var(--primary-dark);
    }

    .impact-stat span {
      font-size: 0.84rem;
      color: #065f46;
      font-weight: 500;
    }

    footer {
      text-align: center;
      padding: 2rem 1rem;
      color: var(--text-muted);
      font-size: 0.85rem;
      border-top: 1px solid var(--border-light);
      background: #ffffff;
    }
  </style>
</head>
<body>

  <header>
    <div class="badge">🌿 Community Ecological Solid Waste Initiative</div>
    <h1>Barangay Waste Segregation AI Scanner &amp; Guide</h1>
    <p>Point your camera or upload a photo of any household waste item to instantly identify whether it is Biodegradable or Non-Biodegradable.</p>
  </header>

  <main class="container">
    <!-- AI SCANNER SECTION -->
    <section class="scanner-card" aria-label="AI Waste Scanner">
      <div class="scanner-header">
        <div class="scanner-title">
          <h2>Live Waste Classifier</h2>
          <span>Powered by Google Teachable Machine • 2-Class Recognition</span>
        </div>
        <div class="mode-controls">
          <button id="btn-webcam" class="btn btn-primary" onclick="startWebcam()">
            📷 Start Webcam
          </button>
          <button id="btn-stop" class="btn btn-danger" onclick="stopWebcam()" style="display: none;">
            ⏹ Stop Camera
          </button>
          <label for="file-upload" class="btn btn-outline">
            📁 Upload Photo
          </label>
          <input id="file-upload" type="file" accept="image/*" style="display: none;" onchange="handleImageUpload(event)" />
        </div>
      </div>

      <div class="scanner-grid">
        <!-- Camera / Image Preview Viewport -->
        <div>
          <div id="viewport" class="viewport-wrapper">
            <div id="placeholder" class="placeholder-state">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="1.75">
                <path stroke-linecap="round" stroke-linejoin="round" d="M3 9a2 2 0 012-2h.93a2 2 0 001.664-.89l.812-1.22A2 2 0 0110.07 4h3.86a2 2 0 011.664.89l.812 1.22A2 2 0 0018.07 7H19a2 2 0 012 2v9a2 2 0 01-2 2H5a2 2 0 01-2-2V9z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M15 13a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>
              <p><strong>No camera or image active</strong></p>
              <p style="font-size: 0.85rem; margin-top: 0.25rem;">Click "Start Webcam" for real-time scanning or upload a photo of a waste item.</p>
            </div>
            <div id="webcam-container"></div>
            <img id="image-preview" alt="Uploaded waste preview" style="display: none;" />
          </div>
          <div style="text-align: center;">
            <span id="status-badge" class="model-status">⏳ Loading AI Model...</span>
          </div>
        </div>

        <!-- Prediction Bars & Dynamic Sorting Box -->
        <div class="results-panel">
          <div id="instruction-box" class="instruction-box">
            <div class="instruction-label">Sorting Instruction</div>
            <div id="instruction-bin" class="instruction-bin">Ready to Scan Waste</div>
            <div id="instruction-text" class="instruction-text">
              Hold a single waste item clearly in front of the camera or upload a photo to see which barangay bin it belongs to.
            </div>
          </div>

          <div class="confidence-list">
            <!-- Class 1: Biodegradable -->
            <div class="confidence-item">
              <div class="confidence-meta">
                <span>🌱 Biodegradable (Nabubulok)</span>
                <span id="pct-bio">0%</span>
              </div>
              <div class="bar-track">
                <div id="bar-bio" class="bar-fill fill-bio"></div>
              </div>
            </div>

            <!-- Class 2: Non-Biodegradable -->
            <div class="confidence-item">
              <div class="confidence-meta">
                <span>🏙️ Non-Biodegradable (Di-Nabubulok)</span>
                <span id="pct-nonbio">0%</span>
              </div>
              <div class="bar-track">
                <div id="bar-nonbio" class="bar-fill fill-nonbio"></div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- SECTION 1: WHY PROPER SEGREGATION MATTERS -->
    <section class="edu-section">
      <div class="section-heading">
        <div class="section-num">1</div>
        <h2>Why Proper Segregation Matters</h2>
      </div>
      <div class="card-grid">
        <div class="info-card">
          <h3>🌊 Prevents Clogged Canals &amp; Flooding</h3>
          <p>Unsegregated plastics and food scraps swept into street storm drains block waterways. Proper sorting keeps barangay esteros and drainage canals clear during heavy rains and typhoons.</p>
        </div>
        <div class="info-card">
          <h3>🦟 Reduces Disease &amp; Pests</h3>
          <p>Separating wet organic food waste from dry garbage eliminates foul odors and stops breeding grounds for dengue-carrying mosquitoes, flies, and rodents in residential alleys.</p>
        </div>
        <div class="info-card">
          <h3>⚖️ Complies with RA 9003</h3>
          <p>Under the Ecological Solid Waste Management Act (RA 9003), mandatory source segregation is enforced at the household level—unsegregated garbage is strictly subject to "No Segregation, No Collection."</p>
        </div>
      </div>
    </section>

    <!-- SECTION 2: THE 2 WASTE CATEGORIES EXPLAINED -->
    <section class="edu-section">
      <div class="section-heading">
        <div class="section-num">2</div>
        <h2>The 2 Waste Categories Explained</h2>
      </div>
      <div class="card-grid">
        <div class="info-card cat-bio">
          <span class="bin-tag tag-bio">GREEN BIN • NABUBULOK</span>
          <h3>🌱 Biodegradable</h3>
          <p>Organic waste materials that can be broken down by microorganisms into compost and soil nutrients.</p>
          <ul>
            <li>Fruit &amp; vegetable peelings</li>
            <li>Leftover food, fish &amp; meat scraps</li>
            <li>Dry leaves, twigs &amp; garden trimmings</li>
            <li>Eggshells &amp; coffee grounds</li>
          </ul>
        </div>

        <div class="info-card cat-nonbio">
          <span class="bin-tag tag-nonbio">BLACK / BLUE BIN • DI-NABUBULOK</span>
          <h3>🏙️ Non-Biodegradable</h3>
          <p>Inorganic waste materials that do not easily decay and require recycling, disposal, or special handling.</p>
          <ul>
            <li>Plastic bottles, bags &amp; food wrappers</li>
            <li>Cardboard boxes, paper &amp; beverage cans</li>
            <li>Styrofoam, broken glass &amp; ceramics</li>
            <li>Used diapers, sachets &amp; household electronics</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- SECTION 3: COMPOSTING & MRF DROP-OFF TIPS -->
    <section class="edu-section">
      <div class="section-heading">
        <div class="section-num">3</div>
        <h2>Composting &amp; MRF Drop-off Tips</h2>
      </div>
      <div class="card-grid">
        <div class="info-card">
          <h3>🪴 Backyard &amp; Sack Composting</h3>
          <ul>
            <li><strong>Layer Greens &amp; Browns:</strong> Mix wet kitchen scraps (nitrogen) with dry leaves, shredded cardboard, or sawdust (carbon) at a 1:2 ratio to prevent odor.</li>
            <li><strong>Aerate Weekly:</strong> Turn the compost pile or perforated sack once a week and keep it moist like a wrung-out sponge.</li>
            <li><strong>Harvest in 45–60 Days:</strong> Dark, earthy-smelling soil is ready for barangay urban gardens.</li>
          </ul>
        </div>
        <div class="info-card">
          <h3>🏭 Materials Recovery Facility (MRF) Prep</h3>
          <ul>
            <li><strong>Rinse &amp; Dry:</strong> Quickly rinse food residue off plastic bottles, cans, and containers so they remain clean for recycling.</li>
            <li><strong>Flatten &amp; Bundle:</strong> Flatten cardboard boxes and crush plastic bottles to save storage space at home and in collection trucks.</li>
            <li><strong>Separate Hazards:</strong> Keep batteries, chemicals, and busted bulbs separate from regular non-biodegradable trash.</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- SECTION 4: LOCAL COLLECTION SCHEDULE & COMMUNITY IMPACT -->
    <section class="edu-section">
      <div class="section-heading">
        <div class="section-num">4</div>
        <h2>Local Collection Schedule &amp; Community Impact</h2>
      </div>
      <div class="table-wrapper">
        <table>
          <thead>
            <tr>
              <th>Collection Day</th>
              <th>Waste Category</th>
              <th>Assigned Bin / Bag</th>
              <th>Curbside Set-Out Time</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td><strong>Monday, Wednesday, Friday</strong></td>
              <td>🌱 Biodegradable (Nabubulok)</td>
              <td>Green Bin / Compostable Bag</td>
              <td>6:00 AM – 7:30 AM</td>
            </tr>
            <tr>
              <td><strong>Tuesday, Thursday, Saturday</strong></td>
              <td>🏙️ Non-Biodegradable (Di-Nabubulok)</td>
              <td>Black Bin / Blue Sack (or MRF Drop-off)</td>
              <td>6:00 AM – 8:00 AM</td>
            </tr>
          </tbody>
        </table>
      </div>

      <div class="impact-banner">
        <div class="impact-stat">
          <strong>68%</strong>
          <span>Waste Diverted from Landfills</span>
        </div>
        <div class="impact-stat">
          <strong>1,450 kg</strong>
          <span>Monthly Compost Produced</span>
        </div>
        <div class="impact-stat">
          <strong>0</strong>
          <span>Clogged Street Drains in Pilot Puroks</span>
        </div>
      </div>
    </section>
  </main>

  <footer>
    Barangay Ecological Solid Waste Management Committee • Powered by Teachable Machine AI
  </footer>

  <script>
    // Teachable Machine Model URL
    const MODEL_URL = "https://teachablemachine.withgoogle.com/models/BWFWIX8Fd/";

    let model = null;
    let webcam = null;
    let isWebcamRunning = false;
    let animationFrameId = null;

    const statusBadge = document.getElementById("status-badge");
    const viewport = document.getElementById("viewport");
    const placeholder = document.getElementById("placeholder");
    const webcamContainer = document.getElementById("webcam-container");
    const imagePreview = document.getElementById("image-preview");
    const btnWebcam = document.getElementById("btn-webcam");
    const btnStop = document.getElementById("btn-stop");

    // Sorting guidance metadata mapped to the 2 categories
    const CATEGORY_GUIDANCE = {
      biodegradable: {
        key: "bio",
        bin: "🟢 GREEN BIN — Biodegradable (Nabubulok)",
        instruction: "Place in your Green Bin or backyard compost pit. Drain excess liquids first and mix with dry leaves to prevent odor."
      },
      nonbiodegradable: {
        key: "nonbio",
        bin: "🔵 BLACK / BLUE BIN — Non-Biodegradable (Di-Nabubulok)",
        instruction: "Rinse clean and dry if recyclable. Place in your Non-Biodegradable collection bag or bring to the Barangay MRF."
      }
    };

    // Load Teachable Machine Model on page startup
    async function initModel() {
      try {
        const modelURL = MODEL_URL + "model.json";
        const metadataURL = MODEL_URL + "metadata.json";
        model = await tmImage.load(modelURL, metadataURL);
        statusBadge.textContent = "✅ AI Model Ready";
      } catch (err) {
        console.error("Failed to load Teachable Machine model:", err);
        statusBadge.textContent = "⚠️ Error loading AI model. Check connection.";
        statusBadge.style.background = "#fee2e2";
        statusBadge.style.color = "#b91c1c";
      }
    }

    // Start live webcam prediction
    async function startWebcam() {
      if (!model) {
        statusBadge.textContent = "⏳ Please wait, model still loading...";
        return;
      }

      stopWebcam();
      imagePreview.style.display = "none";
      placeholder.style.display = "none";
      webcamContainer.innerHTML = "";

      try {
        const flip = true;
        webcam = new tmImage.Webcam(320, 320, flip);
        await webcam.setup();
        await webcam.play();

        isWebcamRunning = true;
        viewport.classList.add("active");
        webcamContainer.appendChild(webcam.canvas);

        btnWebcam.style.display = "none";
        btnStop.style.display = "inline-flex";
        statusBadge.textContent = "🟢 Live Scanning Active";

        loopWebcam();
      } catch (err) {
        console.error("Webcam access error:", err);
        placeholder.style.display = "block";
        statusBadge.textContent = "⚠️ Camera access denied or unavailable";
      }
    }

    // Stop webcam stream
    function stopWebcam() {
      isWebcamRunning = false;
      if (animationFrameId) {
        cancelAnimationFrame(animationFrameId);
        animationFrameId = null;
      }
      if (webcam) {
        webcam.stop();
        webcam = null;
      }
      webcamContainer.innerHTML = "";
      viewport.classList.remove("active");
      btnWebcam.style.display = "inline-flex";
      btnStop.style.display = "none";

      if (imagePreview.style.display === "none") {
        placeholder.style.display = "block";
      }
      if (model) {
        statusBadge.textContent = "✅ AI Model Ready";
      }
    }

    // Real-time animation loop for webcam
    async function loopWebcam() {
      if (!isWebcamRunning || !webcam) return;
      webcam.update();
      await predictElement(webcam.canvas);
      animationFrameId = requestAnimationFrame(loopWebcam);
    }

    // Handle static image upload
    function handleImageUpload(event) {
      const file = event.target.files[0];
      if (!file) return;

      stopWebcam();
      placeholder.style.display = "none";

      const reader = new FileReader();
      reader.onload = function (e) {
        imagePreview.src = e.target.result;
        imagePreview.style.display = "block";
        viewport.classList.add("active");

        imagePreview.onload = async function () {
          if (!model) await initModel();
          statusBadge.textContent = "🔍 Analyzed Uploaded Photo";
          await predictElement(imagePreview);
        };
      };
      reader.readAsDataURL(file);
    }

    // Map Teachable Machine class labels to Biodegradable vs Non-Biodegradable
    function mapClassKey(className) {
      const name = className.toLowerCase();
      if (name.includes("bio") && !name.includes("non")) return "biodegradable";
      // Everything else (Recyclable, Residual, Hazardous/E-Waste) falls under Non-Biodegradable
      return "nonbiodegradable";
    }

    // Run inference on video canvas or uploaded image element
    async function predictElement(htmlElement) {
      if (!model) return;
      const predictions = await model.predict(htmlElement);

      let bioScore = 0;
      let nonBioScore = 0;

      predictions.forEach((pred) => {
        const key = mapClassKey(pred.className);
        if (key === "biodegradable") {
          bioScore += pred.probability;
        } else {
          nonBioScore += pred.probability;
        }
      });

      // Normalize if necessary
      const total = bioScore + nonBioScore;
      if (total > 0) {
        bioScore = bioScore / total;
        nonBioScore = nonBioScore / total;
      }

      // Update UI bars
      updateBar("bio", bioScore);
      updateBar("nonbio", nonBioScore);

      // Determine top prediction
      const topCategory = bioScore >= nonBioScore ? "biodegradable" : "nonbiodegradable";
      const highestProb = Math.max(bioScore, nonBioScore);

      // Update dynamic sorting box
      if (highestProb >= 0.40) {
        const info = CATEGORY_GUIDANCE[topCategory];
        const box = document.getElementById("instruction-box");
        box.className = "instruction-box " + info.key;
        document.getElementById("instruction-bin").textContent = info.bin;
        document.getElementById("instruction-text").textContent = info.instruction;
      } else {
        const box = document.getElementById("instruction-box");
        box.className = "instruction-box";
        document.getElementById("instruction-bin").textContent = "Low Confidence — Adjust Item";
        document.getElementById("instruction-text").textContent =
          "Move the item closer to the camera in good lighting with a plain background for an accurate reading.";
      }
    }

    function updateBar(suffix, probability) {
      const pct = Math.round(probability * 100);
      document.getElementById(`pct-${suffix}`).textContent = `${pct}%`;
      document.getElementById(`bar-${suffix}`).style.width = `${pct}%`;
    }

    // Initialize model immediately on load
    window.addEventListener("DOMContentLoaded", initModel);
  </script>
</body>
</html>
