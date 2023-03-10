English | [繁體中文](README_TCH.md)

# How-to-install-controlNet
A respository help you install controlNet

# Stable Diffusion Webui
Before introduce controlNet. I will recommend you install Stable Diffusion Webui. It will be easier to follow the instruction below.

If you met any problems while instaling Stable Diffusion Webui. You can see this repo: [Lets-start-install-stable-diffusion](https://github.com/JingShing/Lets-start-install-stable-diffusion/blob/main/README.md)。

# controlNet

Extensions we need：
* sd-webui-controlnet
* openpose-editor

The extensions above can be install by GUI in the latest Stable Diffusion Webui.

Please go to extension. Choose Available and click Load from button. It will load a list from the website like the image below.

![ex1](image/ex1.png)

Find
* sd-webui-controlnet
* openpose-editor

Click install.

![ex2](image/ex2.png)

After installed. Go to installed. See is it installed successfully?(If it doesn't display you can use reload to refresh page)

![ex3](image/ex3.png)

Please click check for updates to see is it the latest version.(If it is not the latest version. You can check outdated extentions and click apply to update. Remember use reload to refresh page)

---
# OpenPose Editor
After installed. You can see OpenPose Editor on the menu list.(If it doesn't display. You can use reload or restart Stable Diffusion Webui)

![pose1](image/pose1.png)

You can use Detect from image to load pose from image. It can use manually adjust pose. (Before detect you may need to adjust resolution or size)

![pose2](image/pose2.png)

This is detect from image. It may not work to well. You can adjust it by yourself.

![pose3](image/pose3.png)
![posture](image/pose_detect.png)

After adjust by hand. (head side. Two points inside are eyes. Two points outside are ears.)

You can choose to sent to txt2img(Using text to generate image) or img2img(Using image to generate image). I will use txt2img as example.

---
# ControlNet in txt2img
You can see it has extra part in txt2img which is added by ControlNet.

Using this area you need to [download controlNet model](https://huggingface.co/webui/ControlNet-modules-safetensors/blob/main/control_openpose-fp16.safetensors). After download. Put it in Stable diffusion Webui folder:

```stable-diffusion-webui\extensions\sd-webui-controlnet\models```

If ControlNet area didn't load model successfully. It is recommend you to reload or restart Stable diffusion Webui.

![control1](image/control1.png)

It will have several options to check. Remember checked enable to use controlNet pose as reference. If you have less vram you can also check low-vram to reduce vram demand.

![control2](image/control2.png)

After enter prompt and parameters you can started generate images. Output image will add a openpose for you can use in next time.

Output image and pose:

![out1](image/out_image.png)
![out2](image/out_pose.png)
