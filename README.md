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
安裝成功的話，就可以看到選單多了一個 OpenPose Editor 。(如果有成功 installed ，但沒有出現此選單，可以考慮 reload 或 重啟 Stable Diffusion Webui)

![pose1](image/pose1.png)

可以點選 Detect from image 使用圖片來讀取姿勢，亦或是使用手動的方式調整火柴人的姿勢。(detect 時，記得將解析度/比例調整正確，否則辨識的結果可能不會很理想)

![pose2](image/pose2.png)

這個是自動辨識的結果，並不是特別準確，需要自己手動調整。

![pose3](image/pose3.png)
![posture](image/pose_detect.png)

手動調整過後。(頭的部分，內兩點是眼睛，外兩點是耳朵)

可以選擇將調整過後的火柴人送到 txt2img(以字生圖) 或 img2img(以圖生圖) 中做為參考。以下將以 txt2img 作為範例。

---
# ControlNet in txt2img
延續上面，將調整過後的火柴人送到 txt2img，可以看到 txt2img 底下多出了一個 controlNet 的區塊。

使用此區塊需要[下載 controlNet 特製的模型](https://huggingface.co/webui/ControlNet-modules-safetensors/blob/main/control_openpose-fp16.safetensors)，下載完後，放入 Stable diffusion Webui 安裝資料夾底下：

```stable-diffusion-webui\extensions\sd-webui-controlnet\models```

如果 ControlNet 區塊的 model 沒有讀取到模型的話，建議 reload 或是重啟 Stable diffusion Webui。

![control1](image/control1.png)

底下有不同的選下可以勾選，記得要勾選 enable 才會使用 controlNet 的姿勢做為參考。如果顯存不足也可以開啟 low-vram 來減輕顯卡負擔。

![control2](image/control2.png)

填入關鍵詞後，調整好參數，就可以生成圖片了。輸出的圖片會附上先前調整的 openpose 的圖片，記得保存可以用於下次使用。

輸出的圖片和先前調整的姿勢：

![out1](image/out_image.png)
![out2](image/out_pose.png)
