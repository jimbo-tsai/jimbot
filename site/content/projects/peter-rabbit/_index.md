---
title: "Peter Rabbit Writing Station"
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
    }
    
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

    .rig-card {
        background-color: #d67ab1; 
        border-radius: 20px;
        padding: 2vw;
        color: #ffffff !important;
        text-align: center;
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
<p style="color: #60435f; font-size: 4rem; font-weight: bold; margin: 0; padding: 0; white-space: nowrap;">Peter Rabbit Writing Station</p>
</div>

<div style="display: block; width: 100%; text-align: center; margin: 4vh auto 2vh auto;">
    {{< image width="70%" class="rounded-0" src="build.png" >}}
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

<div style="display: block; width: 100%; text-align: center; margin: 4vh auto 2vh auto;">
    {{< image width="70%" class="rounded-0" src="poster-peter-rabbit.jpg" >}}
</div>

{{% box color="yellow" %}}
The center console storage system, called the Twist n’ Burrow, is a vertical shelf
that seamlessly slides into the table when not in use, and is equipped with two handles
on top to be easily pulled out when access to materials is needed. This integrated system
is spacious, weatherproof, user-friendly, and modular. Below are the first and second iterations of the Twist n' Burrow design, made with 2 and 3 legs respectively.
{{% /box %}}

<div style="width: 100%; display: flex; justify-content: center; margin: 2vh 0;">
<div class="flex-container" style="display: flex; flex-direction: row !important; align-items: center; justify-content: center; gap: 2vw; flex-wrap: nowrap; width: 100%;">

<div style="flex: 1; width: 50%; max-width: 50%;">
<model-viewer 
id="assembly-viewer-1"
src="peter-rabbit-2-leg.gltf" 
camera-controls 
disable-zoom
auto-rotate 
shadow-intensity="1.5"
shadow-softness="0"
exposure="0.6" 
environment-image="legacy"
powerPreference="high-performance"
interaction-prompt="none">
    <div slot="poster" class="model-skeleton"></div>
</model-viewer>
</div>

<div style="flex: 1; width: 50%; max-width: 50%;">
<model-viewer 
id="assembly-viewer-2"
src="peter-rabbit-3-leg.gltf" 
camera-controls 
disable-zoom
auto-rotate 
shadow-intensity="1.5"
shadow-softness="0"
exposure="0.5" 
environment-image="legacy"
powerPreference="high-performance"
interaction-prompt="none">
    <div slot="poster" class="model-skeleton"></div>
</model-viewer>
</div>

</div>
</div>

{{% box color="yellow" %}}
The tree-stumped themed mailbox, named the Hop n’ Hear, provides audio
feedback when a letter is delivered. The mailbox is also weatherproof and user friendly,
but highlights child accessibility and engagement. Additionally, the audio feedback is
powered by an electrical system, allowing the Arboretum to add any features they want
in the future.
{{% /box %}}

<div style="display: block; width: 100%; text-align: center; margin: 4vh auto 2vh auto;">
{{< paige/gallery width="60%" class="rounded-0" images="treestump.jpg" />}}
</div>


<div class="container" style="max-width: 80vw; margin-top: 12vh; padding: 4vh 2vw; text-align: center;">
    <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1.5rem; flex-wrap: wrap; gap: 1rem;">
        <h3 style="font-family: 'Lexend Deca', sans-serif; color: #60435f; margin: 0; text-align: left;">Project Documentation</h3>
        
<a href="peter-rabbit-report.pdf#toolbar=1" 
    target="_blank" 
    style="font-family: 'Lexend Deca', sans-serif; background-color: #60435f; color: #ffffff !important; padding: 0.5rem 1.2rem; border-radius: 8px; text-decoration: none !important; font-size: 0.9rem; transition: background-color 0.2s;" 
    onmouseover="this.style.backgroundColor='#d67ab1'" 
    onmouseout="this.style.backgroundColor='#60435f'">
    View in Another Tab
</a>
</div>
      
<div style="width: 100%; height: 80vh; border-radius: 15px; overflow: hidden; border: 1px solid #60435f; margin: 0 auto;">
    <iframe 
        src="peter-rabbit-report.pdf#toolbar=0" 
        width="100%" 
        height="100%" 
        style="border: none;">
    </iframe>
</div>
</div>

{{% box color="yellow" %}}
In future implementation, the vertical storage system should utilize 3 studs and 3
guide rails should be used instead of the 2 demonstrated in our prototype for stability.
Additionally, further testing with the flap length of the mailbox slots is encouraged to
make sure children cannot get their hands stuck in the slots.
{{% /box %}}

</div>
</div>

<div style="margin-top: 5vh;">
    {{< masonry-slim images="*.jpg" width="20vw" loading="lazy" process="webp" >}}
</div>