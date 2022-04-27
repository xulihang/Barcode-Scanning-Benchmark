# Barcode-Scanning-Benchmark

A benchmark on five 5-second videos. There are four EAN13 video in different angles and one QR code video. Two SDKs are used and compared: [Dynamsoft Barcode Reader](https://www.dynamsoft.com/barcode-reader/overview/) and [ZXing](https://github.com/journeyapps/zxing-android-embedded).

The video is shot using CameraX on Sharp Aquos S2. The benchmark is run on it as well. You can find the Android benchmark app [here](https://github.com/xulihang/CameraXVideo).

The benchmark is done in two modes: frame mode which reads every frames and video mode which emulates live scan.

## Statistics

General:

1. Number of frames processed
2. Number of frames processed with barcodes found
3. First found barcode result

Frame mode: index of the first frame with barcodes found

Video mode: video position of the first frame with barcodes found

You can see the statistics [here](https://blog.xulihang.me/Barcode-Scanning-Benchmark/?path=result.json).

## Conclusion

### SDKs Comparison

We can see that Dynamsoft Barcode Reader has a better decoding rate and quicker to find a barcode. It can read barcodes in various angles while ZXing can only read upright barcodes.

### How to Quickly Scan a Barcode

Based on the test, at the beginning of the video, the frame images may be dark and out of focus. The SDKs spend a lot of time on decoding these frames. We can skip these frames to improve speed. Dynamsoft Camera Enhancer is useful in this aspect as it can filter out blurry frames.


