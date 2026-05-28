---
title: "Jimmy Tsai"
date: "2025-10-18T11:05:01-05:00"
resources:
- src: "*.jpg"
  name: "image"
paige:
  search:
    hide_page: true
  style: |
    /* HIDE STAR CANVAS ON HOME (Critical for CPU) */
    canvas#star-canvas, .paige-star-effect { display: none !important; }

    #paige-collections, #paige-metadata, #paige-sections, #paige-pages { display: none; }
    
    /* 1. BALANCED RENDERING */
    img {
        image-rendering: auto; 
        max-width: 100%;
        height: auto;
        content-visibility: auto;
    }

    body {
        -webkit-font-smoothing: antialiased;
        text-rendering: optimizeSpeed;
    }

    /* 2. OPTIMIZED ANIMATIONS */
    .enlargening-target { 
        opacity: 0;
        transform: translate3d(0, 10px, 0);
        transition: transform 0.6s cubic-bezier(0.2, 0, 0.2, 1), opacity 0.6s ease-in-out !important;
        cursor: pointer;
        display: block;
        border-radius: 1rem;
        will-change: transform, opacity;
    }

    .enlargening-target.revealed {
        opacity: 1;
        transform: translate3d(0, 0, 0);
    }

    .enlargening-target:hover { 
        transform: translate3d(0, 0, 0) !important; 
    }

    .color-change-target {
        transition: color 0.3s ease, transform 0.3s ease !important;
        cursor: default;
        display: block;
        width: fit-content;
        text-decoration: none;
    }
    
    .color-change-target:hover { 
        color: #f3a400 !important; 
        transform: scale(1.01); 
    }

    /* 3. LITE YOUTUBE STYLES - FIXED FOR THUMBNAIL CONTAINMENT */
    .video-wrapper {
        position: relative;
        padding-bottom: 56.25%; /* 16:9 Aspect Ratio */
        height: 0;
        background: #000;
        cursor: pointer;
        overflow: hidden;
    }
    .video-wrapper img {
        position: absolute; 
        top: 0;
        left: 0;
        width: 100%; 
        height: 100%; 
        object-fit: contain; /* Ensures the image is fully visible within the black box */
    }
    .play-button {
        width: 68px; height: 48px; position: absolute; top: 50%; left: 50%;
        transform: translate(-50%, -50%); background-color: rgba(0,0,0,0.7);
        border-radius: 12%; transition: all 0.2s;
        z-index: 2;
    }
    .video-wrapper:hover .play-button { background-color: #f00; }

    /* 4. SLIDESHOW FORMATTING FROM CODE BLOCK TWO */
    .paige-slideshow-wrapper {
        width: 100vw;
        position: relative;
        left: 50%;
        right: 50%;
        margin-left: -50vw;
        margin-right: -50vw;
        display: flex;
        flex-direction: row;
        align-items: stretch;
        background: transparent;
        overflow: hidden;
        min-height: 450px;
        padding-top: 8vh; /* Added space above the slideshow area */
    }

    .slideshow-text-panel {
        width: 25vw;
        display: flex;
        flex-direction: column;
        justify-content: center;
        padding: 2rem 2rem 2rem 4rem; 
        box-sizing: border-box;
    }

    .slideshow-carousel-panel {
        width: 75vw; 
        position: relative;
        display: flex;
    }

    .slideshow-track {
        display: flex;
        width: 100%;
        overflow-x: auto;
        overflow-y: hidden; /* Fixes vertical scroll bleed */
        touch-action: pan-x; /* Restricts touch interactions exclusively to horizontal swiping */
        scroll-snap-type: x mandatory;
        scroll-behavior: smooth;
        scrollbar-width: none;
        -ms-overflow-style: none;
        gap: 40px; 
        padding-left: 20px;
        padding-right: 40vw; /* Keeps space at the end to scroll seamlessly */
    }
    .slideshow-track::-webkit-scrollbar { display: none; }

    .slideshow-slide {
        flex: 0 0 auto; 
        scroll-snap-align: start; 
        display: flex;
        align-items: center;
        justify-content: flex-start;
        opacity: 1; /* Ensure slides load fully visible offscreen */
    }

    .slide-img {
        width: auto;
        max-width: 65vw; 
        height: auto;
        max-height: 70vh;
        object-fit: contain;
    }

    /* FIXED: SMOOTH IMAGE FADE-IN FOR SLIDESHOW IMAGES */
    .slideshow-slide img {
        opacity: 0;
        transition: opacity 0.8s ease-in-out;
        will-change: opacity;
    }

    .slideshow-slide img.img-loaded {
        opacity: 1 !important;
    }

    /* Nav Controls */
    .slide-nav-btn {
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        background: rgba(0, 0, 0, 0.05); 
        color: #333;
        border: none;
        border-radius: 50%;
        width: 44px;
        height: 44px;
        cursor: pointer;
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 10;
        backdrop-filter: blur(4px);
        transition: all 0.2s;
    }
    .slide-nav-btn:hover { background: rgba(0, 0, 0, 0.12); }
    .prev-btn { left: 1rem; }
    .next-btn { right: 2rem; } 

    @media (max-width: 992px) {
        .paige-slideshow-wrapper { flex-direction: column; padding-top: 4vh; }
        .slideshow-text-panel { width: 100vw; padding: 2rem; text-align: center; }
        .slideshow-carousel-panel { width: 100vw !important; }
        .slide-img { max-width: 80vw; }
        .slideshow-track { gap: 20px; padding-right: 20vw; }
    }
---

<script>
(function() {
    function initStaggeredFade() {
        const targets = document.querySelectorAll('.enlargening-target');
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const idx = Array.from(targets).indexOf(entry.target);
                    setTimeout(() => {
                        window.requestAnimationFrame(() => entry.target.classList.add('revealed'));
                    }, idx * 80);
                    observer.unobserve(entry.target);
                }
            });
        }, { threshold: 0.1 });
        targets.forEach(t => observer.observe(t));
    }

    /* FIXED: WATCH AND FADE IN SLIDESHOW IMAGES ON LOAD */
    function initSlideshowFade() {
        const slideImages = document.querySelectorAll('.slideshow-slide img');
        
        slideImages.forEach(img => {
            // Check if browser has already processed or cached the image
            if (img.complete && img.naturalWidth > 0) {
                img.classList.add('img-loaded');
            } else {
                img.addEventListener('load', () => {
                    img.classList.add('img-loaded');
                });
                // Fail-safe: display layout if image breaks
                img.addEventListener('error', () => {
                    img.classList.add('img-loaded');
                });
            }
        });
    }

    window.loadVideo = function(container) {
        const id = container.getAttribute('data-id');
        container.innerHTML = `<iframe style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" src="https://www.youtube.com/embed/${id}?autoplay=1&rel=0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`;
    };

    document.addEventListener("DOMContentLoaded", () => {
        initStaggeredFade();
        initSlideshowFade();
    });
})();
</script>

<div class="paige-slideshow-wrapper">
    <div class="slideshow-text-panel">
        <div class="color-change-target" style="margin-bottom: 2vw;">
            <p class="mb-0" style="font-size: clamp(1.2rem, 3vw, 2.2rem); font-family: 'Lexend Deca', sans-serif; line-height: 1.1; text-align: left;">
                Photographer.<br>Filmmaker.<br>Engineer.
            </p>
        </div>
        <div class="color-change-target">
            <p class="mb-0" style="font-size: 1rem; line-height: 1.6; text-align: left;">
                I'm a student at Northwestern University studying chemical engineering. I like taking photos and making films.
            </p>
        </div>
    </div>

<div class="slideshow-carousel-panel">
<div class="slideshow-track" id="track-main-gallery">

{{< dynamic-slides >}}

</div>

<button class="slide-nav-btn prev-btn" aria-label="Previous image" onclick="document.getElementById('track-main-gallery').scrollBy({ left: -window.innerWidth * 0.65, behavior: 'smooth' })">
<svg viewBox="0 0 24 24" width="24" height="24" stroke="currentColor" stroke-width="2.5" fill="none" stroke-linecap="round" stroke-linejoin="round"><polyline points="15 18 9 12 15 6"></polyline></svg>
</button>
<button class="slide-nav-btn next-btn" aria-label="Next image" onclick="document.getElementById('track-main-gallery').scrollBy({ left: window.innerWidth * 0.65, behavior: 'smooth' })">
<svg viewBox="0 0 24 24" width="24" height="24" stroke="currentColor" stroke-width="2.5" fill="none" stroke-linecap="round" stroke-linejoin="round"><polyline points="9 18 15 12 9 6"></polyline></svg>
</button>
</div>
</div>

<div style="background-color: #ffb61f; width: 100vw; position: relative; left: 50%; right: 50%; margin-left: -50vw; margin-right: -50vw; padding: 5vh 0; margin-top: 12vh;">
<div id="video-section-container" style="display: flex; flex-wrap: wrap; gap: 4vw; align-items: center; justify-content: center; width: 95%; max-width: 1800px; margin: 0 auto; text-align: left;">

<div style="flex: 1; min-width: 300px; color: #fff; padding: 2vw; text-align: left;">
<h2 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(1.5rem, 4vw, 2.5rem); color: #fff; margin-top: 0; text-align: left;">El Palo Alto: A Living Legend</h2>
<p style="font-size: 1.1rem; line-height: 1.6; color: rgba(255,255,255,0.9); text-align: left;">The history and health of the thousand year old El Palo Alto redwood tree. A comprehensive health study </p>
</div>

<div style="flex: 1.5; min-width: 300px; width: 100%;">
<div class="video-wrapper" data-id="sQ5if51uSE8" onclick="loadVideo(this)">
    <img src="https://img.youtube.com/vi/sQ5if51uSE8/maxresdefault.jpg" alt="Video Poster" loading="eager">
    <div class="play-button">
        <svg viewBox="0 0 68 48" style="width:100%; height:100%; fill:white;"><path d="M66.52,7.74c-0.78-2.93-2.49-5.41-5.42-6.19C55.79,0.13,34,0,34,0S12.21,0.13,6.9,1.55 c-2.93,0.78-4.64,3.26-5.42,6.19C0.06,13.05,0,24,0,24s0.06,10.95,1.48,16.26c0.78,2.93,2.49,5.41,5.42,6.19 C12.21,47.87,34,48,34,48s21.79-0.13,27.1-1.55c2.93-0.78,4.64-3.26,5.42-6.19C67.94,34.95,68,24,68,24S67.94,13.05,66.52,7.74z"></path><path d="M 45,24 27,14 27,34" fill="black"></path></svg>
    </div>
</div>
</div>
</div>
</div>

<div style="width: 100%; margin: 8vh auto; min-height: 40vh;">
<div style="display: flex; flex-wrap: wrap; gap: 5vw; align-items: center; justify-content: center; width: 100%;">
<div class="enlargening-target" style="flex: 0 0 40%; min-width: 300px;">
{{< paige/image alt="Deering Snow" class="object-fit-cover h-100 rounded-0" src="zdeering_snow.jpg" loading="eager" decoding="async" >}}
</div>
<div style="flex: 0 0 40%; min-width: 300px; text-align: center;">
<h3 style="font-family: 'Lexend Deca', sans-serif;">Contact me at:</h3>
<a href="mailto:info.jimbot@gmail.com" class="color-change-target" style="margin: 0 auto; color: black; font-size: 1.8rem; font-weight: bold;">info.jimbot@gmail.com</a>
</div> 
</div> 
</div>