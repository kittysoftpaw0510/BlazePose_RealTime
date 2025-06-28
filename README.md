# JS AI Body Tracker

A JavaScript library for real-time human pose estimation using TensorFlow.js. Supports webcam, video files, and online streams.

## Features

- Real-time pose detection in browser
- Multiple video sources: webcam, video files, online streams
- Three AI models: MoveNet, PoseNet, BlazePose
- 3D pose visualization
- Single file library - no Node.js required

## Quick Start

```html
<canvas id="canvas" width="500" height="500"></canvas>
<video id="video" width="500" height="500" style="display:none"></video>

<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs-core"></script>
<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs-converter"></script>
<script src="https://cdn.jsdelivr.net/npm/@tensorflow/tfjs-backend-webgl"></script>
<script src="https://cdn.jsdelivr.net/npm/@tensorflow-models/pose-detection"></script>
<script src="./js/tracker.js"></script>

<script>
tracker.setModel('MoveNetSinglePoseLightning');
tracker.elCanvas = '#canvas';
tracker.elVideo = '#video';
tracker.run('camera');
</script>
```

## Video Sources

```js
tracker.run('camera');  // Webcam
tracker.run('video');   // Video file
tracker.run('stream');  // Online stream
```

## Models

- `MoveNetSinglePoseLightning` - Fast single person
- `MoveNetMultiPoseLightning` - Fast multiple people
- `BlazePoseLite` - 3D pose estimation
- `PoseNetMobileNetV1` - Lightweight
- `PoseNetResNet50` - High accuracy

## Configuration

```js
tracker.pointWidth = 6;    // Line width
tracker.pointRadius = 8;   // Point size
tracker.minScore = 0.35;   // Detection threshold
tracker.enable3D = true;   // 3D visualization
```

## Events

```js
tracker.on('beforeupdate', function(poses) {
    console.log('Detected poses:', poses);
});
```

## Live Demo

https://szczyglis.dev/js-ai-body-tracker

## License

MIT License | 2022 Marcin 'szczyglis' Szczygliński

