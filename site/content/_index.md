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

    /* This class is applied individually by the script */
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
                // 300ms base delay + (150ms * position in the grid)
                // This forces a "waterfall" sequence even if all load at once
                const staggeredDelay = 100 + (index * 100);
                
                setTimeout(() => {
                    target.classList.add('revealed');
                }, staggeredDelay);
            };

            if (img) {
                if (img.complete) {
                    triggerFade();
                } else {
                    img.addEventListener('load', triggerFade);
                    img.addEventListener('error', triggerFade);
                }
            }
        });
    }
    document.addEventListener("DOMContentLoaded", initStaggeredFade);
})();
</script>

<div id="main-grid" style="display: flex; gap: 1vw; align-items: stretch; justify-content: center; width: 95%; max-width: 1800px; margin: 0 auto; min-height: 85vh; flex-wrap: nowrap;">

<div style="flex: 1; min-width: 30%; display: flex; flex-direction: column; gap: 1vw;">
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Sunset Cloud" class="object-fit-cover h-100 rounded-4" src="taiwan_sunset_cloud.jpg" width="100%" >}}
</div>
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Herb Store" class="object-fit-cover h-100 rounded-4" src="herb_store.jpg" width="100%" >}}
</div>
</div>

<div style="flex: 1; min-width: 30%; display: flex; flex-direction: column; gap: 1vw;">
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Urbex Church" class="object-fit-cover h-100 rounded-4" src="urbex_church.jpg" width="100%" >}}
</div>
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Sunset Signal" class="object-fit-cover h-100 rounded-4" src="sunset_signal.jpg" width="100%" >}}
</div>
</div>

<div style="flex: 1; min-width: 30%; display: flex; flex-direction: column; gap: 1vw;">
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Sewing Man" class="object-fit-cover h-100 rounded-4" src="sewing_man.jpg" width="100%" >}}
</div>
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="B&W Car" class="object-fit-cover h-100 rounded-4" src="car_bw.jpg" width="100%" >}}
</div>
<div class="enlargening-target" style="flex: 1;">
{{< paige/image alt="Bay Redwood" class="object-fit-cover h-100 rounded-4" src="bay_redwood_forest.jpg" width="100%" >}}
</div>
</div>

<div style="flex: 1.2; min-width: 30%; display: flex; flex-direction: column; gap: 2vw; justify-content: center; padding-left: 1.5vw;">
<div class="color-change-target">
<p class="mb-0" style="font-size: clamp(1.2rem, 1.5vw, 2.2rem); font-family: 'Lexend Deca', sans-serif; line-height: 1.1; text-align: left;">
Photographer.<br>Filmmaker.<br>Engineer.
</p>
</div>
<div class="color-change-target">
<p class="mb-0" style="font-size: clamp(0.8rem, 0.9vw, 1rem); line-height: 1.6; text-align: left;">
I'm a student at Northwestern University studying chemical engineering. I like taking photos and making films in my free time. Check out some of my work!
</p>
</div>
</div>

</div>