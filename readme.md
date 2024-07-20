# 🎥 HLS Adaptive Bitrate Streaming

Welcome to the HLS Adaptive Bitrate Streaming project! This project utilizes Amazon S3, FFmpeg, and Video.js to provide adaptive video streaming. 

## 📦 Project Overview

This project allows you to upload videos to an S3 bucket, transcode them into HLS format using FFmpeg, and stream them using Video.js.

## 🚀 Features

- 📁 Upload videos to an S3 bucket
- 🎞️ Transcode videos to HLS format with multiple bitrates using FFmpeg
- 📺 Stream videos using Video.js for adaptive bitrate streaming
- 🌐 CORS enabled for cross-origin access

## 🛠️ Technologies Used

- **Amazon S3**: Storage for video files and HLS segments
- **FFmpeg**: Transcoding videos to HLS format
- **Video.js**: Video player for adaptive bitrate streaming

## 📄 Prerequisites

- **AWS Account**: To create and manage the S3 bucket
- **Node.js**: For running the server
- **FFmpeg**: Installed on your system

## 🏁 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/kathan-shah1893/hls-streaming-project.git
cd hls-streaming-project
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Set Up CORS Configuration for S3

Add the following CORS configuration to your S3 bucket:

```json
[
  {
    "AllowedHeaders": [
      "*"
    ],
    "AllowedMethods": [
      "GET",
      "HEAD"
    ],
    "AllowedOrigins": [
      "*"
    ],
    "ExposeHeaders": [
      "ETag"
    ],
    "MaxAgeSeconds": 3000
  }
]
```

### 6. Serve the HTML Player

Serve the `index.html` file to stream the video using Video.js. You can use a simple HTTP server for this:

```bash
npx serve .
```

Navigate to `http://localhost:5000` in your browser to see the video player.

## 📂 Project Structure

```
hls-streaming-project/
│
├── videos/                  # Directory for original videos
├── transcode.js             # Script to transcode videos and upload to S3
├── index.html               # HTML file for Video.js player
├── package.json             # Project dependencies
└── README.md                # Project documentation
```

## 🎬 Usage

### Transcode Script (`transcode.js`)

This script uses FFmpeg to transcode videos in the `videos` directory into HLS format and uploads the segments to the specified S3 bucket.

### Video.js Player (`index.html`)

This HTML file includes the Video.js player setup to stream the HLS content from S3.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HLS Streaming with Video.js</title>
  <link href="https://vjs.zencdn.net/7.14.3/video-js.css" rel="stylesheet" />
</head>
<body>
  <video id="my-video" class="video-js vjs-default-skin" controls preload="auto" width="640" height="264">
    <source src="https://your-bucket-name.s3.your-region.amazonaws.com/Output/index.m3u8" type="application/x-mpegURL">
  </video>
  <script src="https://vjs.zencdn.net/7.14.3/video.js"></script>
</body>
</html>
```

Replace the `src` attribute with your actual S3 bucket URL.

## 🙏 Acknowledgements

- [FFmpeg](https://ffmpeg.org/) for their powerful media processing tools
- [Amazon S3](https://aws.amazon.com/s3/) for reliable and scalable storage
- [Video.js](https://videojs.com/) for the versatile and robust video player

---

Made with ❤️ by [kathan Shah](https://github.com/kathan-shah1893)