---
paige:
  search:
    hide_page: true
  style: |
    #paige-collections, #paige-metadata, #paige-sections, #paige-pages { display: none; }
    
    .enlargening-target { 
        opacity: 0;
        transform: translateY(10px);
        transition: transform 0.8s cubic-bezier(0.25, 1, 0.5, 1), opacity 0.8s ease-in-out !important;
        cursor: pointer;
        backface-visibility: hidden;
        display: block;
        border-radius: 1rem;
    }

    .enlargening-target.revealed {
        opacity: 1;
        transform: translateY(0);
    }

    .enlargening-target:hover { transform: scale(1.03) !important; }

    .color-change-target {
        transition: all 0.4s ease !important;
        cursor: default;
        display: block;
        width: fit-content;
        text-decoration: none;
    }
    .color-change-target:hover { color: #f3a400 !important; transform: scale(1.03); }

    /* MOBILE DETECTOR */
    @media (max-width: 768px) {
        #main-grid { 
            flex-direction: column !important; 
            flex-wrap: wrap !important; 
            height: auto !important;
            gap: 5vw !important;
        }
        /* Forces the inner divs to take full width on mobile */
        #main-grid > div { 
            width: 100% !important; 
            min-width: 100% !important; 
            flex: none !important;
        }
        /* Moves text to the top on mobile */
        .mobile-text-order {
            order: -1 !important;
            padding-left: 0 !important;
            margin-bottom: 2rem;
        }
    }
title: "Jimmy Tsai"
date: "2025-10-18T11:05:01-05:00"
---

<script>
(function() {
    function initStaggeredFade() {
        const targets = document.querySelectorAll('.enlargening-target');
        targets.forEach((target, index) => {
            const img = target.querySelector('img');
            const triggerFade = () => {
                const staggeredDelay = 100 + (index * 100);
                setTimeout(() => {
                    target.classList.add('revealed');
                }, staggeredDelay);
            };
            if (img) {
                if (img.complete) { triggerFade(); } 
                else { img.addEventListener('load', triggerFade); img.addEventListener('error', triggerFade); }
            }
        });
    }
    document.addEventListener("DOMContentLoaded", initStaggeredFade);
})();
</script>

<div id="main-grid" style="display: flex; gap: 1vw; align-items: stretch; justify-content: center; width: 95%; max-width: 1800px; margin: 0 auto; min-height: 85vh; flex-wrap: nowrap;">

<div style="flex: 1; min-width: 30%; display: flex; flex-direction: column; gap: 1vw;">
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Sunset Cloud" class="object-fit-cover h-100 rounded-0" src="taiwan_sunset_cloud.jpg" width="100%" >}}
</div>
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Herb Store" class="object-fit-cover h-100 rounded-0" src="herb_store.jpg" width="100%" >}}
</div>
</div>

<div style="flex: 1; min-width: 30%; display: flex; flex-direction: column; gap: 1vw;">
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Urbex Church" class="object-fit-cover h-100 rounded-0" src="urbex_church.jpg" width="100%" >}}
</div>
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Sunset Signal" class="object-fit-cover h-100 rounded-0" src="sunset_signal.jpg" width="100%" >}}
</div>
</div>

<div style="flex: 1; min-width: 30%; display: flex; flex-direction: column; gap: 1vw;">
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Sewing Man" class="object-fit-cover h-100 rounded-0" src="sewing_man.jpg" width="100%" >}}
</div>
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="B&W Car" class="object-fit-cover h-100 rounded-0" src="car_bw.jpg" width="100%" >}}
</div>
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Bay Redwood" class="object-fit-cover h-100 rounded-0" src="bay_redwood_forest.jpg" width="100%" >}}
</div>
</div>

<div class="mobile-text-order" style="flex: 1.2; min-width: 30%; display: flex; flex-direction: column; gap: 2vw; justify-content: center; padding-left: 1.5vw;">
<div class="color-change-target">
<p class="mb-0" style="font-size: clamp(1.2rem, 3vw, 2.2rem); font-family: 'Lexend Deca', sans-serif; line-height: 1.1; text-align: left;">
Photographer.<br>Filmmaker.<br>Engineer.
</p>
</div>
<div class="color-change-target">
<p class="mb-0" style="font-size: clamp(1rem, 4vw, 1rem); line-height: 1.6; text-align: left;">
I'm a student at Northwestern University studying chemical engineering. I like taking photos and making films in my free time. Check out some of my work!
</p>
</div>
</div>

</div>



<div style="background-color: #f3a400; width: 100vw; position: relative; left: 50%; right: 50%; margin-left: -50vw; margin-right: -50vw; padding: 5vh 0; margin-top: 5vh;">
<div id="video-section-container" style="display: flex; flex-wrap: wrap; gap: 4vw; align-items: center; justify-content: center; width: 95%; max-width: 1800px; margin: 0 auto;">

<div style="flex: 1; min-width: 300px; color: #fff; padding: 2vw;">
<div class="color-change-target" style="cursor: default;">
<h2 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(1.5rem, 4vw, 2.5rem); margin-bottom: 1.5rem; color: #fff !important;">
El Palo Alto: A Living Legend
</h2>
</div>
<div class="color-change-target" style="cursor: default;">
<p style="font-size: 1.1rem; line-height: 1.6; color: rgba(255,255,255,0.9) !important;">
This documentary explores the incredible 1,000-year history of the El Palo Alto redwood tree. 
From its survival through centuries of environmental changes to its role as the namesake of 
Palo Alto, California, this tree stands as a symbol of resilience.
</p>
</div>
</div>

<div style="flex: 1.5; min-width: 300px; width: 100%;">
<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden;">
<iframe 
style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;"
src="https://www.youtube.com/embed/sQ5if51uSE8?rel=0&modestbranding=1" 
title="YouTube video player" 
allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
allowfullscreen>
</iframe>
</div>
</div>
</div>
</div>

<div style="width: 95%; max-width: 1800px; margin: 8vh auto; min-height: 40vh;">
<div style="display: flex; flex-wrap: wrap; gap: 1vw; align-items: stretch;">

<div class="enlargening-target" style="flex: 1; min-width: 300px; display: flex;">
{{< paige/image alt="Deering Snow" class="object-fit-cover h-100 rounded-0" src="deering_snow.jpg" width="100%" >}}
</div>

<div style="flex: 1; min-width: 300px; display: flex; flex-direction: column; justify-content: center; padding: 2vw; text-align: center;">

<div class="color-change-target" style="color: black; transition: color 0.4s ease;">
    <h3 style="font-family: 'Lexend Deca', sans-serif; font-size: 1.8rem; margin: 0;">
        Contact me at: info.jimbot@gmail.com
    </h3>
</div>

<div style="display: flex; justify-content: center; align-items: center; gap: 20px; margin-top: 20px;">
    <a href="mailto:info.jimbot@gmail.com" class="color-change-target" style="color: black; text-decoration: none; transition: all 0.4s ease;">
        <i class="bi bi-envelope" style="font-size: 2.5rem;"></i>
    </a>
</div>

</div>



</p>
</div>

</div>
</div>

</div>
</div>