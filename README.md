# Compute Stochastic Screen Space Reflections
Compute Stochastic Screen Space Reflections for Unity post processing. Utilizing shared memory for performance.
Should be mostly production ready, except for a few Hierarchical Z-depth casting artifacts.

# Contents
* [Features](#Features)
* [Requirements](#Requirements)
* [Installation](#Installation)
* [Usage](#Usage)
* [References](#References)
* [Showcase](#Showcase)
* [Real life usage](#Real-life-usage)
* [Screenshots](#Screenshots)
* [Before and After](#Before-and-After)
* [Performance](#Performance)

# Features
* Hierarchical Z-depth casting
* Temporal reflection depth reprojection
* Median Filtering for extra denoising
* Reflection Color Mipmap Pyramid
* Raycast and resolve pass downsampling
* Frame reprojection for faking multiple bounces
* Specular elongation
* Contact hardening

# Requirements
* Works only with deferred rendering
* Compute shader capable video card
* [Unity Post Processing v2](https://github.com/Unity-Technologies/PostProcessing)
* Tested with Unity 2018.2

# Installation
It should work anywhere inside the assets folder but it is recommended putting it in the `Packages` folder.

# Usage
Just add a new effect in a post processing profile under `Custom/Stochastic Screen Space Reflections`

# References
* Rewritten from [Xerxes1138](https://github.com/Xerxes1138/StochasticScreenSpaceReflection)
* Based mainly on [Tomasz Stachowiak and Yasin Uludag, Siggraph15](https://www.ea.com/frostbite/news/stochastic-screen-space-reflections)

# Showcase
https://www.youtube.com/watch?v=9D0kRA7vSCQ

https://www.youtube.com/watch?v=LuLO25cPwyI

# Real life usage
https://www.youtube.com/watch?v=MtAYmqzJM5g

# Screenshots

![](https://i.imgur.com/Fxfu70R.png)
![](https://i.imgur.com/C37mrdB.png)
![](https://i.imgur.com/QcsCOpf.png)
![](https://i.imgur.com/4NefLT8.png)

# Before and After
![Before](https://i.imgur.com/DzvKm5I.png) ![After](https://i.imgur.com/Ua2Ng1R.png)

# Performance
Tested on a GTX 1070 at 1080p

* Highest Quality, High Quality Blur
	* Raycasting: 1.4 ms
	* Blur: 0.73 ms
	* Temporal: 0.67 ms
	* Resolve: 0.55 ms
	* **Total + Others: 4.15 ms**

* Raycast and Resolved downsampled, Low Quality Blur
	* Raycasting: 0.5 ms
	* Temporal: 0.19 ms
	* Resolve: 0.19 ms
	* **Total + Others: 1.7 ms**