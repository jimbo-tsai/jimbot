---
categories: ["content", "paige"]
date: "2025-10-18T11:07:00-05:00"
description: "A camera rig I made for my Fujifilm XT-4, made from aluminum extrusions"
title: "DIY Camera Rig"
weight: 10
paige:
  style: |
    #paige-collections, #paige-metadata, #paige-sections, #paige-pages { display: none; }
    
    #star-bg, canvas#star-canvas, .paige-star-effect { 
        position: fixed !important; 
        z-index: -1 !important; 
        display: block !important; 
    }

    model-viewer {
        width: 100%;
        height: 500px;
        background-color: transparent;
        filter: contrast(1.1) brightness(0.9) saturate(1.2);
        --poster-color: transparent;
    }

    /* Box now only wraps the text content */
    .rig-card {
        background-color: #f3a400; 
        border-radius: 20px;
        padding: 2vw;
        color: #ffffff !important;
    }

    .container { padding-top: 0 !important; }

    @media (max-width: 768px) {
        model-viewer { height: 350px; }
        .flex-container { flex-direction: column !important; }
        .rig-card { width: 100%; }
    }
---

<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>

<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 0 2vw 5vh 2vw;">
    <div style="text-align: left; margin-bottom: 2vh; padding-top: 2vh;">
        <h1 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(2rem, 5vw, 3rem); color: white; margin: 0;">
            Full Assembly
        </h1>
        <p style="color: #000000; font-size: 4rem; font-weight: bold; margin: 0;">Fujifilm XT-4 Cage Assembly</p>
    </div>

>I wanted to create a handle for my Fujifilm X-T4 so I could hold it to stabilize video shots. The Smallrig camera cage for the X-T4 costs around $70-$80 and that's out of my price range of $0 unfortunately, so I wanted to make a usable design that could be made for much more affordably (at the cost of bulk and weight). From scratch, the materials used are not free, but I was able to source everything from the Northwestern shop. This design is the fifth iteration of the camera rig, but there are a lot more to improve about the design. Additional changes in the design will be reflected as I update the website. 

<div class="flex-container" style="display: flex; align-items: center; gap: 0vw;">
<div style="flex: 1.5; min-width: 40vw;">
    <model-viewer 
        id="assembly-viewer"
        src="Assembly.gltf" 
        camera-controls 
        auto-rotate 
        shadow-intensity="1.5"
        shadow-softness="0"
        exposure="0.8" 
        environment-image="legacy"
        powerPreference="high-performance"
        interaction-prompt="none">
    </model-viewer>
</div>

<div class="rig-card" style="flex: 1; min-width: 300px;">
    <h3 style="font-family: 'Lexend Deca', sans-serif; margin-top: 0; color: #ffffff;">Specs</h3>
    <ul style="line-height: 1.8; list-style-type: none; padding-left: 0; font-size: 0.95rem; color: #ffffff;">
        <li><strong>Size:</strong> A x Y x C mm</li>
        <li><strong>Weight:</strong> To be Weighed</li>
        <li><strong>Assembly Time:</strong> 30 min</li>
    </ul>
</div>
</div>
</div>


<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 5vh 2vw;">
<div class="flex-container" style="display: flex; align-items: flex-start; gap: 4vw;">

<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 5vh 2vw;">
    <!-- flex: stretch ensures both columns take the height of the tallest element -->
    <div class="flex-container" style="display: flex; align-items: stretch; gap: 2vw; flex-wrap: wrap;">

<!-- Left Side: Materials List -->
<div style="flex: 1; min-width: 20vw; display: flex;">
    <div class="rig-card" style="width: 100%; height: 100%; background-color: #f3a400; box-sizing: border-box; display: flex; flex-direction: column;">
       <h3 style="font-family: 'Lexend Deca', sans-serif; margin-top: 0; color: #ffffff;">Materials</h3>
        <ul style="line-height: 3; list-style-type: disc; padding-left: 1 rem; font-size: 0.95rem; color: #ffffff;">
            <li>2020 Aluminum Extrusion</li>
            <li>2020 L Corner Connecter</li>
            <li>2020 Sliding T Nuts</li>
            <li>10-32 3/8" Hex Screws</li>
            <li>10-32 Washers</li>
            <li>1" Diameter Wood Dowels</li>
            <li>Small Wood Screw</li>
            <li>PLA Plastic</li>
        </ul>
    </div>
</div>

<!-- Right Side: Gallery -->
<div style="flex: 1.5; min-width: 30vw;">
    {{< paige/gallery width="100%" class="rounded-5" images="cage1.jpg" />}}
</div>


<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 0 2vw 10vh 2vw;">
    <div style="text-align: left; margin-bottom: 2vh; padding-top: 2vh;">
        <h1 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(2rem, 5vw, 3rem); color: white; margin: 0;">
            DIY Camera Rig
        </h1>
        <p style="color: #000000; font-size: 1.1rem; font-weight: bold; margin: 0;">XT-4 Attachment Base</p>
    </div>

>3D printed with PLA using a gyroid inner pattern and 25% infill. 

<div class="flex-container" style="display: flex; align-items: center; gap: 1vw;">
<div style="flex: 1.5; min-width: 40vw;">
    <model-viewer 
        id="cage-viewer"
        src="CameraCageV5.gltf" 
        camera-controls 
        auto-rotate 
        shadow-intensity="1.5"
        shadow-softness="0"
        exposure="0.8" 
        environment-image="legacy"
        powerPreference="high-performance"
        interaction-prompt="none">
    </model-viewer>
</div>

<div class="rig-card" style="flex: 1; min-width: 300px;">
    <h3 style="font-family: 'Lexend Deca', sans-serif; margin-top: 0; color: #ffffff;">Base Specs</h3>
    <ul style="line-height: 1.8; list-style-type: none; padding-left: 0; font-size: 0.95rem; color: #ffffff;">
        <li><strong>Print:</strong> Black Bambulab PLA</li>
        <li>
            <a href="CameraCageV5.3mf" download style="color: #ffffff; text-decoration: underline;">
                📥 Download CameraCage_V5
            </a>
        </li>
    </ul>
</div>
</div>
</div>

{{< paige/gallery width="100%" class="rounded-5" images="cage2.jpg" />}}