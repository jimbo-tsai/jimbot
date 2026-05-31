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

<div style="text-align: center; margin: -6vh 0 0 0 !important; padding: 0;">
<h1 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(2rem, 5vw, 3rem); color: white; margin: 0; padding: 0;"></h1>
<p style="color: #60435f; font-size: 4rem; font-weight: bold; margin: 0; padding: 0; white-space: nowrap;">6MWT Timer</p>
</div>

<div style="display: block; width: 100%; text-align: center; margin: 4vh auto 2vh auto;">
{{< paige/gallery width="70%" class="rounded-0" images="build.png" />}}
</div>

<script type="module" src="https://ajax.googleapis.com/ajax/libs/model-viewer/4.0.0/model-viewer.min.js"></script>

<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 0 2vw 5vh 2vw; text-align: center;">

{{% box color="yellow" %}}
As a part of Design Thinking and Communication (DTC), the Morton Arboretum presented the challenge of creating a Peter Rabbit
themed writing station as a part of a new Peter Rabbit’s Garden section they are creating
in the Children’s Garden. The purpose of this project is to design structures that will
encourage children to practice their literacy skills by writing letters, as well as making
the space easily maintainable for Arboretum staff. In the development of our solution,
several interviews were conducted with various staff members of the Arboretum to gain
a deeper understanding of the current practices and core principles of the Children’s
Garden. The major need of this challenge was to engage the kids with the station and to
provide effective storage solutions for the stationery and letters to facilitate their
experience. The proposed solution consists of two parts: a center console storage
system, and a tree-stumped themed mailbox.
{{% /box %}}
