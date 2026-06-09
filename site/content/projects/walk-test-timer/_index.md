---
title: "6MWT Timer"
paige:
  style: |
    #paige-collections, #paige-metadata, #paige-sections, #paige-pages { display: none; }
    
    #star-bg, canvas#star-canvas, .paige-star-effect { 
        position: fixed !important; 
        z-index: -1 !important; 
        display: block !important; 
    }

    #paige-header {
        position: sticky !important;
        top: 0;
        z-index: 1050 !important;
        background-color: #ffffff !important; /* Force the clean white background wrapper to stay solid while scrolling */
    }
    
    /* MINIMAL ADDITION: Fade and lift keyframes */
    @keyframes slideUpFade {
        from {
            opacity: 0;
            transform: translateY(20px);
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    /* MINIMAL ADDITION: Animation container style */
    .project-animate-wrapper {
        opacity: 0;
        animation: slideUpFade 1s cubic-bezier(0.25, 1, 0.5, 1) forwards;
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
        text-align: center; /* Centers text inside the boxes */
    }

    .container { padding-top: 0 !important; }

    @media (max-width: 768px) {
        model-viewer { height: 350px; }
        .flex-container { flex-direction: column !important; }
        .rig-card { width: 100%; }
    }
---

<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 0 2vw 5vh 2vw;">

<div class="project-animate-wrapper">

<div style="text-align: center; margin: -6vh 0 0 0 !important; padding: 0;">
<h1 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(2rem, 5vw, 3rem); color: white; margin: 0; padding: 0;"></h1>
<p style="color: #60435f; font-size: 4rem; font-weight: bold; margin: 0; padding: 0; white-space: nowrap;">6MWT Timer</p>
</div>

<div style="display: block; width: 100%; text-align: center; margin: 4vh auto 2vh auto;">
{{< image width="40%" class="rounded-0" images="build.png" >}}
</div>

<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>

<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 0 2vw 5vh 2vw; text-align: center;">

{{% box color="yellow" %}}
As a part of Design Thinking and Communication (DTC), Dr. Gina Clark at the Shirley Ryan Ability Lab presented a problem regarding the 6 Minute Walk Test (6MWT). She regularly administers the 6MWT to measure how far patients can walk in six minutes as an indicator of rehabilitation progress. During the test, she holds a rolling measuring wheel in one hand and supports the patient with the other, leaving no free hand to check a timer and making it difficult to monitor elapsed time without compromising patient safety. To address this, our proposed solution is an attachment for the measuring wheel that keeps a phone timer visible and accessible throughout the 6MWT, allowing the physical therapist to monitor time without releasing either the patient or the measuring wheel.
{{% /box %}}




<div class="container" style="max-width: 80vw; margin-top: 12vh; padding: 4vh 2vw; text-align: center;">
    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem; flex-wrap: wrap; gap: 1rem;">
        <h3 style="font-family: 'Lexend Deca', sans-serif; color: #60435f; margin: 0; text-align: left;">Project Documentation</h3>
        
<a href="6mwt-report.pdf#toolbar=1" 
    target="_blank" 
    style="font-family: 'Lexend Deca', sans-serif; background-color: #60435f; color: #ffffff !important; padding: 0.5rem 1.2rem; border-radius: 8px; text-decoration: none !important; font-size: 0.9rem; transition: background-color 0.2s;" 
    onmouseover="this.style.backgroundColor='#d67ab1'" 
    onmouseout="this.style.backgroundColor='#60435f'">
    View in Another Tab
</a>
</div>
      
<div style="width: 100%; height: 80vh; border-radius: 15px; overflow: hidden; border: 1px solid #60435f; margin: 0 auto;">
    <iframe 
        src="6mwt-report.pdf#toolbar=0" 
        width="100%" 
        height="100%" 
        style="border: none;">
    </iframe>
</div>
</div>

</div> 
</div> 
</div> 

<div style="margin-top: 3vh;">
    {{< masonry-slim images="*.jpg" width="20vw" loading="lazy" process="webp" >}}
</div>