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
    
    /* 1. BALANCED RENDERING - FIXED: Removed flicker-inducing content-visibility */
    img {
        image-rendering: auto; 
        max-width: 100%;
        height: auto;
    }

    body {
        -webkit-font-smoothing: antialiased;
        text-rendering: optimizeSpeed;
    }

    /* 2. OPTIMIZED ANIMATIONS - FIXED: Added backface hidden rules to lock GPU scaling layer */
    .enlargening-target { 
        opacity: 0;
        transform: translate3d(0, 14px, 0);
        transition: transform 0.6s cubic-bezier(0.2, 0, 0.2, 1), opacity 0.6s ease-in-out !important;
        cursor: pointer;
        display: block;
        border-radius: 0px !important; 
        will-change: transform, opacity;
        -webkit-backface-visibility: hidden;
        backface-visibility: hidden;
        transform-style: preserve-3d;
    }

    .enlargening-target.revealed {
        opacity: 1;
        transform: translate3d(0, 0, 0);
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

    /* 3. LITE YOUTUBE STYLES */
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
        object-fit: contain;
    }
    .play-button {
        width: 68px; height: 48px; position: absolute; top: 50%; left: 50%;
        transform: translate(-50%, -50%); background-color: rgba(0,0,0,0.7);
        border-radius: 12%; transition: all 0.2s;
        z-index: 2;
    }
    /* FIXED: Corrected invalid 5-character hex token string */
    .video-wrapper:hover .play-button { background-color: #ffffff; }
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

    window.loadVideo = function(container) {
        const id = container.getAttribute('data-id');
        container.innerHTML = `<iframe style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;" src="https://www.youtube.com/embed/${id}?autoplay=1&rel=0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>`;
    };

    document.addEventListener("DOMContentLoaded", () => {
        initStaggeredFade();
    });
})();
</script>

{{< masonry-gallery class="rounded-0" >}}{{< /masonry-gallery >}}

<div style="width: 100vw; position: relative; left: 50%; right: 50%; margin-left: -50vw; margin-right: -50vw; padding: 6vh 0; margin-top: 4xvh;">
    <div id="video-section-container" style="display: flex; flex-direction: column; gap: 3vh; align-items: flex-start; justify-content: center; width: 90%; max-width: 1400px; margin: 0 auto; text-align: left;">

<div style="width: 100%; color: #228B22; padding: 1vw; text-align: left;">
    <h2 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(1.5rem, 4vw, 2.3rem); color: #228B22; margin-top: 0; text-align: left; font-weight: 700;">El Palo Alto: A Living Legend</h2>
    <p style="font-size: 1.05rem; line-height: 1.6; color: #228B22; text-align: left;">The history and health of the thousand year old El Palo Alto redwood tree. A comprehensive health study.</p>
</div>

<div style="width: 100%;">
    <div style="border: 0.5rem solid forestgreen; width: 100%; box-sizing: border-box;">
        <div class="video-wrapper" data-id="sQ5if51uSE8" onclick="loadVideo(this)">
            <img src="https://img.youtube.com/vi/sQ5if51uSE8/maxresdefault.jpg" alt="Video Poster" loading="lazy">
            <div class="play-button">
                <svg viewBox="0 0 68 48" style="width:100%; height:100%; fill:white;">
                    <path d="M66.52,7.74c-0.78-2.93-2.49-5.41-5.42-6.19C55.79,0.13,34,0,34,0S12.21,0.13,6.9,1.55 c-2.93,0.78-4.64,3.26-5.42,6.19C0.06,13.05,0,24,0,24s0.06,10.95,1.48,16.26c0.78,2.93,2.49,5.41,5.42,6.19 C12.21,47.87,34,48,34,48s21.79-0.13,27.1-1.55c2.93-0.78,4.64-3.26,5.42-6.19C67.94,34.95,68,24,68,24S67.94,13.05,66.52,7.74z"></path>
                    <path d="M 45,24 27,14 27,34" fill="black"></path>
                </svg>
            </div>
        </div>
    </div>
</div>

</div>
</div>

<div style="max-width: 1400px; margin: 10vh auto 6vh auto; padding: 0 2rem;">
    <div style="display: flex; flex-wrap: wrap; gap: 4vw; align-items: center; justify-content: center; width: 100%;">
        
{{< dynamic-frame.inline >}}
    {{- $img := .Page.Resources.GetMatch "zdeering_snow.jpg" }}
    {{- $imgColor := "rgb(238, 238, 238)" }}
    
    {{- if $img }}
        {{- $hexMap := dict "0" 0 "1" 1 "2" 2 "3" 3 "4" 4 "5" 5 "6" 6 "7" 7 "8" 8 "9" 9 "a" 10 "b" 11 "c" 12 "d" 13 "e" 14 "f" 15 }}
        {{- $sumR := 0 }} {{- $sumG := 0 }} {{- $sumB := 0 }} {{- $totalWeight := 0 }}
        
        {{- if $img.Colors }}
        {{- range $img.Colors }}
            {{- $c := lower . }}
            {{- $r := add (mul (index $hexMap (substr $c 1 1)) 16) (index $hexMap (substr $c 2 1)) }}
            {{- $g := add (mul (index $hexMap (substr $c 3 1)) 16) (index $hexMap (substr $c 4 1)) }}
            {{- $b := add (mul (index $hexMap (substr $c 5 1)) 16) (index $hexMap (substr $c 6 1)) }}
            
            {{- $lum := add (add (mul $r 299) (mul $g 587)) (mul $b 114) }}
            {{- $weight := div $lum 1000 }}
            {{- if eq $weight 0 }}{{ $weight = 1 }}{{ end }}
            
            {{- $weightSq := mul $weight $weight }}
            
            {{- $sumR = add $sumR (mul $r $weightSq) }}
            {{- $sumG = add $sumG (mul $g $weightSq) }}
            {{- $sumB = add $sumB (mul $b $weightSq) }}
            {{- $totalWeight = add $totalWeight $weightSq }}
        {{- end }}
        
        {{- if gt $totalWeight 0 }}
            {{- $avgR := div $sumR $totalWeight }}
            {{- $avgG := div $sumG $totalWeight }}
            {{- $avgB := div $sumB $totalWeight }}
            {{- $imgColor = printf "rgb(%d, %d, %d)" $avgR $avgG $avgB }}
        {{- end }}
        {{- end }}
    {{- end }}

<div class="enlargening-target" style="flex: 1; min-width: 300px; max-width: 500px; background-color: {{ $imgColor | safeCSS }}; padding: 0.3rem;">
    {{- if $img }}
        <img src="{{ $img.RelPermalink }}" class="object-fit-cover w-100 rounded-0" alt="Deering Snow" loading="lazy" decoding="sync">
    {{- else }}
        <img src="{{ "zdeering_snow.jpg" | relURL }}" class="object-fit-cover w-100 rounded-0" alt="Deering Snow" loading="lazy" decoding="sync">
    {{- end }}
</div>
{{< /dynamic-frame.inline >}}

<div style="flex: 1; min-width: 300px; text-align: center;">
<h3 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(1.3rem, 2.5vw, 1.8rem); margin-bottom: 1rem; font-weight: 700;">Contact me at:</h3>
<a href="mailto:info.jimbot@gmail.com" class="color-change-target" style="margin: 0 auto; color: black; font-size: clamp(1.3rem, 3vw, 2rem); font-weight: bold; letter-spacing: -0.02em;">info.jimbot@gmail.com</a>
</div> 
</div> 
</div>