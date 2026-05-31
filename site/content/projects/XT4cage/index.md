---
categories: ["content", "paige"]
date: "2025-10-18T11:07:00-05:00"
description: "A camera rig I made for my Fujifilm XT-4, made from aluminum extrusions"
title: "DIY Camera Rig"
weight: 0
paige:
  style: |
    #paige-collections, #paige-metadata, #paige-sections, #paige-pages { display: none; }
    #star-bg, canvas#star-canvas, .paige-star-effect { position: fixed !important; z-index: -1 !important; display: block !important; }
    
    /* Make the entire layout block wrapper of the theme header sticky */
    #paige-header {
        position: sticky !important;
        top: 0;
        z-index: 1050 !important;
    }

    model-viewer {
        width: 100%;
        height: 350px;
        background-color: transparent;
        filter: contrast(1.1) brightness(0.9) saturate(1.2);
        --poster-color: transparent;
    }
    #cage-viewer {
        height: 250px !important; 
    }
    .rig-card {
        background-color: #d67ab1; 
        border-radius: 8px;
        padding: 2vw;
        color: #ffffff !important;
        box-sizing: border-box;
    }
    .gallery-wrapper, .gallery-wrapper * {
        height: 100% !important;
        width: 100% !important;
    }
    .container { padding-top: 0 !important; }
    @media (max-width: 768px) {
        model-viewer { height: 200px; }
        #cage-viewer { height: 180px !important; } 
        .flex-container { flex-direction: column !important; }
        .rig-card { width: 100%; }
        .gallery-container { height: auto !important; min-height: 300px; }
    }
---

<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>

<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 0 2vw 5vh 2vw;">

<div style="text-align: center; margin-bottom: 2vh; padding-top: 2vh;">
<p style="color: #60435f; font-size: 4rem; font-weight: bold; margin: 0;">Fujifilm XT-4 Cage</p>
</div>

{{% box color="yellow" %}}
I wanted to create a handle for my Fujifilm X-T4 so I could hold it to stabilize video shots. The Smallrig camera cage for the X-T4 costs around $70-$80 and that's out of my price range of $0 unfortunately, so I wanted to make a usable design that could be made for much more affordably (at the cost of bulk and weight). From scratch, the materials used are not free, but I was able to source everything from the Northwestern shop. This design is the fifth iteration of the camera rig, but there are a lot more to improve about the design. Additional changes in the design will be reflected as I update the website. 
{{% /box %}}

<div class="flex-container" style="display: flex; align-items: center; gap: 2vw; margin-top: 4vh;">
<div style="flex: 1.5; min-width: 40vw;">
    <model-viewer id="assembly-viewer" src="Assembly.gltf" camera-controls auto-rotate shadow-intensity="1.5" shadow-softness="0" exposure="0.8" environment-image="legacy" powerPreference="high-performance" interaction-prompt="none"></model-viewer>
</div>
<div class="rig-card" style="flex: 1; min-width: 300px;">
    <h3 style="font-family: 'Lexend Deca', sans-serif; margin-top: 0; color: #ffffff;">Specs</h3>
    <ul style="line-height: 1.8; list-style-type: none; padding-left: 0; font-size: 0.95rem; color: #ffffff;">
        <li><strong>Size:</strong> 32.1 x 8.3 x 14 cm</li>
        <li><strong>Weight:</strong> 0.28 kg</li>
        <li><strong>Assembly Time:</strong> 30 min</li>
    </ul>
</div>
</div>

<div class="flex-container" style="display: flex; align-items: stretch; gap: 2vw; flex-wrap: wrap; margin-top: 8vh; margin-bottom: 2vh;">
<div style="flex: 1; min-width: 20vw;">
    <div class="rig-card" style="width: 100%; height: 420px; display: flex; flex-direction: column; justify-content: center;">
        <h3 style="font-family: 'Lexend Deca', sans-serif; margin-top: 0; color: #ffffff;">Materials</h3>
        <ul style="line-height: 2.2; list-style-type: disc; padding-left: 1.5rem; font-size: 0.95rem; color: #ffffff; margin-bottom: 0;">
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
<div class="gallery-container" style="flex: 1.5; min-width: 30vw; height: 420px;">
    <div class="gallery-wrapper" style="width: 100%; height: 100%; overflow: hidden; border-radius: 8px;">
        {{< paige/gallery width="100%" height="100%" class="rounded-2" images="cage1.jpg" style="object-fit: cover; height: 100%; width: 100%;" />}}
    </div>
</div>
</div>

<div style="text-align: left; margin-bottom: 2vh; padding-top: 2vh;">
<h1 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(2rem, 5vw, 3rem); color: white; margin: 0;">DIY Camera Rig</h1>
<p style="color: #000000; font-size: 1.1rem; font-weight: bold; margin: 0;">XT-4 Attachment Base</p>
</div>

<div class="flex-container" style="display: flex; align-items: stretch; max-height: 250px; gap: 2vw; margin-top: 4vh; margin-bottom: 6vh; overflow: hidden;">
<div style="flex: 1.5; min-width: 40vw; max-height: 250px;">
    <model-viewer id="cage-viewer" src="CameraCageV5.gltf" camera-controls auto-rotate shadow-intensity="1.5" shadow-softness="0" exposure="0.8" environment-image="legacy" powerPreference="high-performance" interaction-prompt="none"></model-viewer>
</div>
<div class="rig-card" style="flex: 1; min-width: 300px; max-height: 250px; display: flex; flex-direction: column; justify-content: center;">
    <h3 style="font-family: 'Lexend Deca', sans-serif; margin-top: 0; color: #ffffff;">Base Specs</h3>
    <ul style="line-height: 1.6; list-style-type: none; padding-left: 0; font-size: 0.95rem; color: #ffffff; margin-bottom: 0;">
        <li>Print with black Bambulab PLA</li>
        <li>Gyroid inner pattern and 25% infill.</li> 
        <li><a href="CameraCageV5.3mf" download style="color: #ffffff; text-decoration: underline;">📥 Download CameraCage_V5</a></li>
    </ul>
</div>
</div>

{{< masonry-slim images="*.jpg" width="20vw" loading="lazy" process="webp" >}}

</div>