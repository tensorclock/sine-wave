<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sine Wave Visualization</title>
    <style>
        :root {
            /* Palette based on dataviz reference: neutral surfaces and a clear signal hue */
            --bg-color: #ffffff;
            --surface-color: #f8f9fa;
            --text-primary: #1a1a1a;
            --text-muted: #666666;
            --signal-color: #2563eb; /* Vibrant blue for the primary signal */
            --grid-color: #e5e7eb;
            --accent-color: #ef4444; /* Red for the sampling point */

            /* Dark mode variables */
            --bg-dark: #111827;
            --surface-dark: #1f2937;
            --text-primary-dark: #f9fafb;
            --text-muted-dark: #9ca3af;
            --grid-dark: #374151;
        }

        body.dark-mode {
            --bg-color: var(--bg-dark);
            --surface-color: var(--surface-dark);
            --text-primary: var(--text-primary-dark);
            --text-muted: var(--text-muted-dark);
            --grid-color: var(--grid-dark);
        }

        body {
            margin: 0;
            padding: 0;
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-primary);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            transition: background-color 0.3s ease;
        }

        .container {
            width: 90%;
            max-width: 800px;
            background: var(--surface-color);
            padding: 2rem;
            border-radius: 12px;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }

        .header {
            margin-bottom: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        h1 {
            margin: 0;
            font-size: 1.25rem;
            font-weight: 600;
        }

        .controls {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .control-group {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        label {
            font-size: 0.875rem;
            color: var(--text-muted);
            font-weight: 500;
            display: flex;
            justify-content: space-between;
        }

        input[type="range"] {
            width: 100%;
            cursor: pointer;
        }

        .canvas-container {
            position: relative;
            width: 100%;
            height: 300px;
            border-left: 2px solid var(--text-primary);
            border-bottom: 2px solid var(--text-primary);
            background: var(--bg-color);
            border-radius: 0 0 4px 0;
            overflow: hidden;
        }

        canvas {
            width: 100%;
            height: 100%;
            display: block;
        }

        .theme-toggle {
            background: none;
            border: 1px solid var(--text-muted);
            color: var(--text-primary);
            padding: 0.5rem 1rem;
            border-radius: 6px;
            cursor: pointer;
            font-size: 0.875rem;
            transition: all 0.2s;
        }

        .theme-toggle:hover {
            background: var(--grid-color);
        }

        .stats {
            margin-top: 1rem;
            font-family: monospace;
            font-size: 0.8rem;
            color: var(--text-muted);
            text-align: right;
        }
    </style>
</head>
<body>

    <div class="container">
        <div class="header">
            <h1>Sine Wave Signal</h1>
            <button class="theme-toggle" onclick="document.body.classList.toggle('dark-mode')">🌓 Toggle Theme</button>
        </div>

        <div class="controls">
            <div class="control-group">
                <label>Frequency <span id="freq-val">1.0 Hz</span></label>
                <input type="range" id="frequency" min="0.1" max="5" step="0.1" value="1">
            </div>
            <div class="control-group">
                <label>Amplitude <span id="amp-val">50%</span></label>
                <input type="range" id="amplitude" min="0" max="1" step="0.01" value="0.5">
            </div>
        </div>

        <div class="canvas-container">
            <canvas id="waveCanvas"></canvas>
        </div>

        <div class="stats" id="stats">
            Phase: 0.00 rad
        </div>
    </div>

    <script>
        const canvas = document.getElementById('waveCanvas');
        const ctx = canvas.getContext('2d');
        const freqInput = document.getElementById('frequency');
        const ampInput = document.getElementById('amplitude');
        const freqVal = document.getElementById('freq-val');
        const ampVal = document.getElementById('amp-val');
        const stats = document.getElementById('stats');

        let width, height;
        let phase = 0;

        function resize() {
            const rect = canvas.getBoundingClientRect();
            canvas.width = rect.width * window.devicePixelRatio;
            canvas.height = rect.height * window.devicePixelRatio;
            width = canvas.width;
            height = canvas.height;
            ctx.scale(window.devicePixelRatio, window.devicePixelRatio);
        }

        window.addEventListener('resize', resize);
        resize();

        function draw() {
            ctx.clearRect(0, 0, width / window.devicePixelRatio, height / window.devicePixelRatio);

            const w = width / window.devicePixelRatio;
            const h = height / window.devicePixelRatio;
            const frequency = parseFloat(freqInput.value);
            const amplitude = parseFloat(ampInput.value);

            freqVal.innerText = `${frequency.toFixed(1)} Hz`;
            ampVal.innerText = `${Math.round(amplitude * 100)}%`;

            ctx.beginPath();
            ctx.strokeStyle = getComputedStyle(document.body).getPropertyValue('--grid-color');
            ctx.lineWidth = 1;
            ctx.moveTo(0, h / 2);
            ctx.lineTo(w, h / 2);
            for (let x = 0; x < w; x += w / 10) {
                ctx.moveTo(x, 0);
                ctx.lineTo(x, h);
            }
            ctx.stroke();

            ctx.beginPath();
            ctx.strokeStyle = getComputedStyle(document.body).getPropertyValue('--signal-color');
            ctx.lineWidth = 2;
            ctx.lineJoin = 'round';

            for (let x = 0; x <= w; x++) {
                const t = x / w;
                const angle = 2 * Math.PI * frequency * t + phase;
                const y = (h / 2) + Math.sin(angle) * (h / 2 * amplitude);
                if (x === 0) ctx.moveTo(x, y);
                else ctx.lineTo(x, y);
            }
            ctx.stroke();

            const leadAngle = phase;
            const leadY = (h / 2) + Math.sin(leadAngle) * (h / 2 * amplitude);
            ctx.beginPath();
            ctx.fillStyle = getComputedStyle(document.body).getPropertyValue('--accent-color');
            ctx.arc(0, leadY, 4, 0, Math.PI * 2);
            ctx.fill();

            phase += 0.05;
            if (phase > 2 * Math.PI) phase -= 2 * Math.PI;

            stats.innerText = `Phase: ${phase.toFixed(2)} rad`;
            requestAnimationFrame(draw);
        }

        draw();
    </script>
</body>
</html>
