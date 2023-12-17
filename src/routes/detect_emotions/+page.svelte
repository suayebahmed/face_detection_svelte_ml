<script>
    import { onMount } from 'svelte';
    import * as faceapi from 'face-api.js';

    let video;
    let emotion = '';
    let stream;
    let isStreaming = false;

    // onMount(async () => {
    //     await faceapi.nets.tinyFaceDetector.loadFromUri('/models');
    //     await faceapi.nets.faceExpressionNet.loadFromUri('/models');
    // });

    async function toggleVideo() {
        if (isStreaming) {
            video.srcObject = null;
            if (stream) {
                stream.getTracks().forEach(track => track.stop());
            }
        } else {
            stream = await navigator.mediaDevices.getUserMedia({ video: { width: 500, height: 500 } });
            video.srcObject = stream;
            video.play();

            // setInterval(async () => {
            //     const detections = await faceapi.detectAllFaces(video, new faceapi.TinyFaceDetectorOptions()).withFaceExpressions();
            //     const box = detections.detection.box;
            //     if (box.left !== null && box.top !== null && box.right !==  null && box.bottom !== null) {
            //         new faceapi.draw.DrawBox(box, { label: 'Face' }).draw(canvas);
            //     }
            //     if (detections.length > 0) {
            //         console.log(detections[0].expressions);

            //         const sortedEmotions = detections[0].expressions.asSortedArray().sort((a, b) => b.probability - a.probability);
            //         emotion = sortedEmotions[0].expression;
            //     }
            // }, 100);
        }
        isStreaming = !isStreaming;
    }
</script>

<h1>Face Emotion Detection</h1>
<button on:click={toggleVideo}>{isStreaming ? 'Stop' : 'Start'}</button>
<p></p>
<video bind:this={video} autoplay playsinline>
    <track kind="captions">
</video>
<p>Feeling: {emotion}</p>


<style>
    button {
        padding: 10px 20px;
        border-radius: 5px;
        border: 3px solid yellowgreen;
        margin-top: 0;
        margin-bottom: 10px;
        background-color: transparent;
        cursor: pointer;
    }
</style>