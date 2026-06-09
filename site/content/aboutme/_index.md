---
title: "About Jimmy"
date: "2024-01-18T12:03:00-05:00"
description: ""
paige:
  search:
    hide_page: true
  style: |
    /* Hides collections and sections, but LEAVES the title visible */
    #paige-collections,
    #paige-sections,
    #paige-pages {
        display: none;
    }

    /* NEW: Clean entry keyframes for the upward fade-in */
    @keyframes slideUpFade {
        from {
            opacity: 0;
            transform: translateY(15px); /* Controls the distance of the upward movement */
        }
        to {
            opacity: 1;
            transform: translateY(0);
        }
    }

    /* NEW: Animation wrapper to seamlessly move all elements as one cohesive block */
    .about-animate-wrapper {
        opacity: 0;
        animation: slideUpFade 0.9s cubic-bezier(0.25, 1, 0.5, 1) forwards;
    }

    .enlargening-target { 
        transition: transform 0.6s cubic-bezier(0.25, 1, 0.5, 1) !important;
        cursor: pointer;
        display: block;
        backface-visibility: hidden;
        border-radius: 1rem;
        overflow: hidden;
        width: 100%;
        height: 20rem; 
        margin-bottom: 2rem;
        background-color: rgba(96, 67, 95, 0.05); 
    }

    .enlargening-target:hover {
        transform: scale(1.05) !important;
    }

    .enlargening-target img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: block;
        opacity: 0;
        transition: opacity 0.8s ease-in-out !important;
    }

    .enlargening-target img.loaded {
        opacity: 1;
    }

    /* Locked base text and icon states to Dark Plum */
    .color-change-target {
        color: #60435f !important; 
        transition: color 0.4s ease !important;
        text-decoration: none !important; 
    }

    /* Main highlights stay bright Petal Pink on mouse hover */
    .color-change-target:hover {
        color: #d67ab1 !important;
    }
    
    /* Force the automatic page title to match your homepage's responsive look */
    h1, .paige-header-title, #paige-header h1 {
        font-family: 'Lexend Deca', sans-serif !important;
        font-size: clamp(1.5rem, 4vw, 2.5rem) !important;
        text-align: left !important;
    }
---

<!-- Everything is wrapped here to animate flawlessly without layout popping -->
<div class="about-animate-wrapper">

<div class="enlargening-target">
    <img src="selfie_split.jpg" alt="Jimmy Tsai" onload="this.classList.add('loaded')">
</div>

<div style="max-width: 600px; margin: 0 auto; text-align: justify;">
    <p class="color-change-target">
        Jimmy Tsai is a Taiwanese-American based in the Bay Area and Chicago. Photography and filmmaking are his creative release as he studies his engineering degree. He mainly does street photography, but he's down for any project, big or small. Contact him through email or on Instagram.
    </p>
</div>

<div style="display: flex; justify-content: center; align-items: center; gap: 20px; margin-top: 20px;">
    <a href="https://www.youtube.com/channel/UCQulP0uyasw93322XVnpvZQ" class="color-change-target" target="_blank">
        <i class="bi bi-youtube" style="font-size: 2rem;"></i>
    </a>
    <a href="https://www.instagram.com/jimbot.tsai" class="color-change-target" target="_blank">
        <i class="bi bi-instagram" style="font-size: 2rem;"></i>
    </a>
    <a href="mailto:info.jimbot@gmail.com" class="color-change-target">
        <i class="bi bi-envelope" style="font-size: 2rem;"></i>
    </a>
</div>

</div>