> This is an **unofficial** community project. Not affiliated with the Deep-Live-Cam developers.

> **Disclaimer:** This software can swap faces in real time. If using a real person's face, get their consent and label any output as a deepfake when sharing. You are responsible for how you use it. See the [upstream disclaimer](https://github.com/hacksider/Deep-Live-Cam#disclaimer) for full terms.

# Deep-Live-Cam Builds

Portable builds of [Deep-Live-Cam](https://github.com/hacksider/Deep-Live-Cam) — real-time face swap and video deepfake tool.

**No Python, no pip, no setup.**  Download, extract, run.

![Demo](img/demo.gif)

## Download

Go to [Releases](../../releases/latest) and grab the right build for your setup:

> Don't trust our binaries? Fork this repo and run the workflow yourself.

| Platform | Build | GPU | Dependencies | Recommended for |
|----------|-------|-----|--------------|-----------------|
| Windows | **directml** | Any GPU (NVIDIA / AMD / Intel) | None | Most Windows users |
| Windows | **cuda** | NVIDIA RTX 2000+ | [CUDA 12](https://developer.nvidia.com/cuda-12-9-1-download-archive) + [cuDNN 9](https://developer.nvidia.com/cudnn-downloads) | Best performance on modern NVIDIA |
| Windows | **openvino** | Intel only | None | Best performance on Intel |
| macOS | **coreml** | Apple Silicon | None | Mac M1+ users |

> **Windows** — not sure which one to pick? Go with **directml**. It works on any GPU with no extra setup.

> **CUDA note:** The CUDA build requires RTX 2000 series or newer (GTX 16-series and older may produce visual artifacts due to limited fp16 support). You must install CUDA 12 and cuDNN 9 separately — the launcher will check for them on startup.

If your GPU isn't supported or unavailable, the app automatically falls back to CPU. CPU mode is **much slower** but works on any machine.

## Usage

### Windows

1. Extract the zip
2. Run `DeepLiveCam.bat`
3. Select a source face and click Live


### macOS

1. Extract the zip
2. Double-click `DeepLiveCam.command` — macOS will block it the first time. Go to **System Settings → Privacy & Security**, scroll down and click **Open Anyway**
3. Select a source face and click Live
4. The first time you click **Live**, macOS will ask for camera access. Approve it, then click **Live** again.
5. The first launch on macOS can take around 2 minutes. This is expected; later launches should be much faster.

## Virtual camera (OBS)

To use Deep-Live-Cam in Google Meet, Discord, Zoom, or any other video call app, you need a virtual camera. [OBS Studio](https://obsproject.com/) (free) makes this easy:

1. Open OBS
2. Under Sources, click **+** > **Window Capture** > select the Deep-Live-Cam preview window
3. Click **Start Virtual Camera**
4. In your video call app, choose **OBS Virtual Camera** as the camera

> **Tip:** In OBS, go to Settings > Audio and set all Mic/Auxiliary Audio devices to **Disabled** — otherwise OBS may interfere with your Bluetooth audio quality.

## How builds work

A [GitHub Actions workflow](.github/workflows/build.yml) checks [upstream](https://github.com/hacksider/Deep-Live-Cam) daily at 6 AM UTC for new commits. If anything changed, it builds all variants and publishes a new release.
