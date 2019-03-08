# onion

A tool to help you visiualize your caffe model results. The input source can be mp4 file, rtsp stream or h264 raw data.

feel free to use it, enjoy yourself~

# How to

> * Download [DeepStream](https://developer.nvidia.com/deepstream-sdk-download) 3.0 sdk.
> * tar jxvf DeepStreamSDK-Tesla-v3.0.tbz2
> * cd DeepStream_Release
> * follow the instruction in README to install dependency

```C++
cp -r [Deepstream_tool](https://github.com/NVIDIA-AI-IOT/redaction_with_deepstream) sources/apps/sample_apps/
cd sources/apps/sample_apps/Deepstream_tool 
make
cd -

cp -r objectDetector_desmond sources/
cd sources/objectDetector_desmond
make
cd -
```

# Run 
```C++
cd DeepStream_Release/sources/apps/sample_apps/Deepstream_tool
./deepstream-app -c ../../../objectDetector_desmond/config_infer_primary_SSD.txt -i /your/mp4/file/path
```
here you can see the on screen display. Very interesting. If you are interested in keeping the osd to file, you can add -o option to the command like -o output.mp4.

# FAQ
> * Q. For some mp4 files, the codec return error.
A. Mostly, this results from the h264 bitstream encoding, you can check your mp4 file, it should be h264 encoded mp4 file, you can change the encoding format to avc1. The main difference from h264 and avc1 format is that the former encodes H.264 bitstream without start codes and the latter encodes H.264 bitstream with start codes. You can refer to tools/ffmpeg.txt to reencode your mp4 file.


# Contact
- Desmond desmond.yao@buaa.edu.cn
