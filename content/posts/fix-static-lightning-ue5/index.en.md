+++
categories = ['technical']
date = '2023-03-02T00:00:00+00:00'
draft = false
title = 'Fixing stuff: Static lighting in UE5'
+++

If you're working with UE and having issues with static lighting, this is the post for you.

![Screenshot in UE5 showing static lights with no visible illumination](imgs/static_lightning_error_screenshot.JPG)

This problem occurs because by default, the lighting system in UE5 projects is Lumen. In this post, I won't debate its advantages or disadvantages, but if you want to fix this issue easily—and have a potato PC like mine—follow these steps to continue using static lights 😉

First, go to **Edit > Project Settings**

![Screenshot of UE5 Project Settings menu](imgs/project_settings_menu.JPG)

In Project Settings, search for **Lumen** and select **"None"** in the *Dynamic Global Illumination Method* option.

![Screenshot showing the Dynamic Global Illumination Method option in UE5](imgs/dynamic_global_illumination_method_option.JPG)

After updating this setting, if you've already baked your static lighting, it should immediately appear in your current scene. If not, generate the lighting (bake lighting) and check your results.

![Screenshot of a UE5 scene showing static lights working](imgs/static_lightning_fixed_screenshot.JPG)

> 🖼️ Sunset on the Sea. 1872. John Frederick Kensett
