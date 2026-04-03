# Deep-Live-Cam Builds

Portable Windows builds of [Deep-Live-Cam](https://github.com/hacksider/Deep-Live-Cam) — real-time face swap and video deepfake tool.

**No Python, no pip, no setup.** Download, extract, run. Everything stays inside the folder — no PATH changes, no registry writes, no leftovers.

## Download

Go to [Releases](../../releases/latest) and grab the right build for your GPU:

| Build | GPU | Recommended for |
|-------|-----|-----------------|
| **directml** | Any GPU (NVIDIA / AMD / Intel) | Most users |
| **cuda** | NVIDIA only | Best performance on NVIDIA |
| **openvino** | Intel only | Best performance on Intel |

> Not sure which one to pick? Go with **directml**.

Every build includes a `DeepLiveCam-cpu.bat` fallback if your GPU isn't working.

## Usage

1. Extract the zip
2. Run `DeepLiveCam.bat` (GPU) or `DeepLiveCam-cpu.bat` (CPU fallback)
3. Select a source face and click Live

Close the console window to quit — the X button on the app window doesn't always work.

## Virtual camera (OBS)

To use Deep-Live-Cam in Google Meet, Discord, Zoom, or any other video call app, you need a virtual camera. [OBS Studio](https://obsproject.com/) (free) makes this easy:

1. Open OBS
2. Under Sources, click **+** > **Window Capture** > select the Deep-Live-Cam preview window
3. Click **Start Virtual Camera**
4. In your video call app, choose **OBS Virtual Camera** as the camera

> **Tip:** In OBS, go to Settings > Audio and set all Mic/Auxiliary Audio devices to **Disabled** — otherwise OBS may interfere with your Bluetooth audio quality.

## How builds work

A [GitHub Actions workflow](.github/workflows/build.yml) runs weekly (Monday 6 AM UTC) and checks [upstream](https://github.com/hacksider/Deep-Live-Cam) for new commits. If anything changed, it builds all four variants and publishes a new release.

