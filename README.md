> This is an **unofficial** community project. Not affiliated with the Deep-Live-Cam developers.

# Deep-Live-Cam Builds

Portable builds of [Deep-Live-Cam](https://github.com/hacksider/Deep-Live-Cam) — real-time face swap and video deepfake tool.

![Demo](media/demo.gif)

**No Python, no pip, no setup.** Download, extract, run. Everything stays inside the folder — no PATH changes, no registry writes, no leftovers.

## Download

Go to [Releases](../../releases/latest) and grab the right build for your setup:

| Platform | Build | GPU | Recommended for |
|----------|-------|-----|-----------------|
| Windows | **directml** | Any GPU (NVIDIA / AMD / Intel) | Most Windows users |
| Windows | **cuda** | NVIDIA only | Best performance on NVIDIA |
| Windows | **openvino** | Intel only | Best performance on Intel |
| macOS | **coreml** | Apple Silicon | Mac M1+ users |

> **Windows** — not sure which one to pick? Go with **directml**.

Every build includes a CPU fallback script if your GPU isn't working. CPU mode is **much slower** but works on any machine.

## Usage

### Windows

1. Extract the zip
2. Run `DeepLiveCam.bat`
3. Select a source face and click Live

> To use CPU fallback, run `DeepLiveCam-cpu.bat` instead.

> **Close the console window to quit** — the X button on the app window doesn't always work.

### macOS

1. Extract the zip
2. Right-click `DeepLiveCam.command` and select **Open** (macOS blocks unsigned apps on first launch)
3. Select a source face and click Live

> To use CPU fallback, run `DeepLiveCam-cpu.command` instead.

## Virtual camera (OBS)

To use Deep-Live-Cam in Google Meet, Discord, Zoom, or any other video call app, you need a virtual camera. [OBS Studio](https://obsproject.com/) (free) makes this easy:

1. Open OBS
2. Under Sources, click **+** > **Window Capture** > select the Deep-Live-Cam preview window
3. Click **Start Virtual Camera**
4. In your video call app, choose **OBS Virtual Camera** as the camera

> **Tip:** In OBS, go to Settings > Audio and set all Mic/Auxiliary Audio devices to **Disabled** — otherwise OBS may interfere with your Bluetooth audio quality.

## How builds work

A [GitHub Actions workflow](.github/workflows/build.yml) runs weekly (Monday 6 AM UTC) and checks [upstream](https://github.com/hacksider/Deep-Live-Cam) for new commits. If anything changed, it builds all variants and publishes a new release.
