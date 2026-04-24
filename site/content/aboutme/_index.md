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
    }

    .enlargening-target:hover {
        transform: scale(1.05) !important;
    }

    .enlargening-target img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        display: block;
    }

    .color-change-target {
        transition: color 0.4s ease !important;
        text-decoration: none !important; /* Removes underlines/underscores */
    }

    .color-change-target:hover {
        color: #f3a400 !important;
    }
---

<div class="enlargening-target">
    <img src="selfie_split.jpg" alt="Jimmy Tsai">
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