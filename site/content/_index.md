---
paige:
  search:
    hide_page: true
  style: |
    #paige-collections,
    #paige-metadata,
    #paige-sections,
    #paige-pages {
        display: none;
    }

    .enlargening-target { 
        transition: transform 0.6s cubic-bezier(0.25, 1, 0.5, 1) !important;
        cursor: pointer;
        display: block;
        backface-visibility: hidden;
    }

    .enlargening-target:hover {
        transform: scale(1.02) !important;
    }

    .color-change-target {
        transition: all 0.4s ease !important;
        cursor: default;
        display: inline-block;
    }

    .color-change-target:hover {
        color: #f3a400 !important;
        transform: scale(1.02);
    }
title: "Jimmy Tsai"
date: "2025-10-18T11:05:01-05:00"
---

<div style="display: flex; gap: 3rem; align-items: center; justify-content: center; max-width: 1200px; margin: 0 auto; min-height: 60vh; flex-wrap: wrap;">

<div style="flex: 0 1 40vw; min-width: 300px;" class="enlargening-target">
{{< paige/image alt="Landscape" breakpoints=true class="object-fit-cover rounded-4" fetchpriority="high" loading="eager" process="webp" src="*.jpg" width="100%" >}}
</div>

<div style="flex: 1; min-width: 300px; max-width: 40vw">
<p class="fw-bold mb-2 text-center color-change-target" style="font-size: clamp(1.5rem, 5vw + 0.2rem, 3.5rem) !important; width: 100%;">Hi, Jimmy Tsai here.</p>

<div class="container-fluid">
<div class="justify-content-center row">
<div class="col col-auto px-0">
<p class="lead text-center color-change-target" style="font-size: clamp(1rem, 1.2vw + 0.2rem, 1.5rem) !important; width: 100%;">Photographer. Filmmaker. Engineer.</p>
<p class="lead text-center color-change-target" style="font-size: clamp(0.9rem, 1.1vw + 0.2rem, 1.2rem) !important; width: 100%;">I'm a student at Northwestern University studying chemical engineering. I like taking photos and making films in my free time. Check out some of my work!</p>
</div>
</div>
</div>
</div>

</div>