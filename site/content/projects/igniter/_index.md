---
title: "NUSTARS Igniter"
weight: 10
paige:
  style: |
    /* Force the automatic page title to match your homepage's responsive look */
    h1, .paige-header-title, #paige-header h1 {
        font-family: 'Lexend Deca', sans-serif !important;
        font-size: clamp(1.5rem, 4vw, 2.5rem) !important;
        text-align: left !important;
        color: #60435f !important; /* Kept consistent with dark plum */
    }

    /* SKELETON SHIMMER SYSTEM */
    .model-wrapper {
        position: relative;
        width: 100%;
        height: 500px;
    }

    .model-skeleton {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        /* Shimmer gradient using soft tones of your palette */
        background: linear-gradient(90deg, #fdf7fa 25%, #e2a3c7 50%, #fdf7fa 75%);
        background-size: 200% 100%;
        animation: paigeModelShimmer 1.6s infinite linear;
        border-radius: 8px;
        z-index: 5;
        transition: opacity 0.4s cubic-bezier(0.25, 1, 0.5, 1);
        pointer-events: none;
    }

    @keyframes paigeModelShimmer {
        0% { background-position: 200% 0; }
        100% { background-position: -200% 0; }
    }
---

<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>

<div style="text-align: center; margin: -6vh 0 0 0 !important; padding: 0;">
<h1 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(2rem, 5vw, 3rem); color: var(--clr-dark, #60435f); margin: 0; padding: 0;"></h1>
<p style="color: #60435f; font-size: 4rem; font-weight: bold; margin: 0; padding: 0; white-space: nowrap;">Augmented Spark Igniter</p>
</div>

<div style="display: block; width: 100%; text-align: center; margin: 4vh auto 2vh auto;">
{{< paige/gallery width="70%" class="rounded-0" images="igniter-test-1-3.gif" />}}
</div>

<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 0 2vw 5vh 2vw;">

  <!-- UPDATED: Swapped legacy yellow to new high-contrast teal shortcode setup -->
  {{% box color="teal" %}}
As part of the NUSTARS Propulsion team, we designed an augmented spark igniter (ASI) and igniter test stand to safely and effectively gather test data. The ASI uses a mixture of gaseous oxygen and liquid ethanol to create combustion, releasing energy ~6% of the main engine. The fuel-rich combustion is primarily controlled by pressure on the fuel and oxygen (changes mass flow rate and type of combustion). My primary focus was on safely constructing the igniter test stand and developing testing protocols. The test stand was first designed through a P&ID, then correctly specced to the the specific valves and pressure transducers needed at each point. The CAD was develeoped thereafter and constructed accordingly. Testing protocols were developed in Epsilon3 and used during each hotfire to ensure officer safety. 
  {{% /box %}}

  <div class="flex-container" style="display: flex; align-items: center; gap: 4vw; flex-wrap: wrap; margin-top: 4vh;">

<!-- MODEL 1 WRAPPER WITH SHIMMER BOX -->
<div style="flex: 1; min-width: 35vw; display: flex; justify-content: center;">
  <div class="model-wrapper">
      <div class="model-skeleton" id="skeleton-1"></div>
      <model-viewer 
          id="assembly-viewer-1"
          src="igniter-test-stand.gltf" 
          camera-controls 
          auto-rotate 
          shadow-intensity="1.5"
          shadow-softness="0"
          exposure="0.6" 
          environment-image="legacy"
          powerPreference="high-performance"
          interaction-prompt="none"
          style="width: 100%; height: 500px; background-color: transparent;">
      </model-viewer>
  </div>
</div>

<!-- UPDATED: Swapped legacy blue to new blush accent configuration -->
{{% box color="blush" %}}
The augmented spark igniter was designed to be easily made on a manual mill, through the process took quite a while. I got to learn how to cut, mill, and tap 304 stainless steel to a 10 thou tolerance. In the process of constructing the igniter + test stand, I learned how to use teflon tape to seal threads, how oxygen clean to prevent contaminant ignition, how to leak test, how to use pressure regulators, and more. We also did compressed gas training in order to safely handle gas cylinders and conduct hot fires.
{{% /box %}}

<div style="width: 100%; display: flex; flex-direction: row; align-items: center; justify-content: center; gap: 2vw; flex-wrap: nowrap; margin: 4vh 0;">

  <!-- MODEL 2 WRAPPER WITH SHIMMER BOX -->
  <div style="flex: 1; width: 50%; max-width: 50%; display: flex; justify-content: center;">
      <div class="model-wrapper">
          <div class="model-skeleton" id="skeleton-2"></div>
          <model-viewer 
              id="assembly-viewer-2"
              src="igniter-block.gltf" 
              camera-controls 
              auto-rotate 
              shadow-intensity="1.5"
              shadow-softness="0"
              exposure="0.5" 
              environment-image="legacy"
              powerPreference="high-performance"
              interaction-prompt="none"
              style="width: 100%; height: 500px; background-color: transparent;">
          </model-viewer>
      </div>
  </div>

  <div style="flex: 1; width: 50%; max-width: 50%; text-align: center; margin: 0;">
      {{< paige/gallery width="100%" class="rounded-0" images="mill-block.jpg" />}}
  </div>

</div>

</div>

{{< masonry-slim images="*.jpg" width="20vw" loading="lazy" process="webp" >}}

</div>

<!-- Native execution script handling loading cycles -->
<script>
  (function() {
    function setupModelLoader(viewerId, skeletonId) {
      const viewer = document.getElementById(viewerId);
      const skeleton = document.getElementById(skeletonId);
      
      if (!viewer || !skeleton) return;

      // Fires immediately when asset engine completes download parsing cycle
      viewer.addEventListener('load', () => {
        window.requestAnimationFrame(() => {
          skeleton.style.opacity = '0';
          // Cleanly extract element from resource layout loop after opacity drop completes
          setTimeout(() => skeleton.remove(), 400);
        });
      });
    }

    if (document.readyState === 'loading') {
      document.addEventListener('DOMContentLoaded', () => {
        setupModelLoader('assembly-viewer-1', 'skeleton-1');
        setupModelLoader('assembly-viewer-2', 'skeleton-2');
      });
    } else {
      setupModelLoader('assembly-viewer-1', 'skeleton-1');
      setupModelLoader('assembly-viewer-2', 'skeleton-2');
    }
  })();
</script>