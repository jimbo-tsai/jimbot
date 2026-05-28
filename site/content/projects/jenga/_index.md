---
title: "Jenga"
paige:
  style: |
    #paige-collections, #paige-metadata, #paige-sections, #paige-pages { display: none; }
    
    /* Make the entire layout block wrapper of the theme header sticky */
    #paige-header {
        position: sticky !important;
        top: 0;
        z-index: 1050 !important;
        background-color: #ffffff !important; /* Force the clean white background wrapper to stay solid while scrolling */
    }

    .container { padding-top: 0 !important; }
    
    /* Removes default margins/padding from the Hugo gallery bundle container */
    .paige-gallery, .gallery, [class*="gallery"], [class*="bundle"] {
        margin-bottom: 0 !important;
        padding-bottom: 0 !important;
    }

    /* FORCE YOUTUBE GRID TO STACK VERTICALLY */
    .vertical-video-stack > div, 
    .vertical-video-stack {
        display: flex !important;
        flex-direction: column !important;
        align-items: center !important;
        width: 100% !important;
        gap: 4vh !important; /* Adds space between the stacked videos */
    }

    /* Ensures the video players scale nicely when stacked */
    .vertical-video-stack iframe,
    .vertical-video-stack .video-wrapper,
    .vertical-video-stack [class*="video"] {
        width: 100% !important;
        max-width: 800px !important; /* Prevents the video from becoming too wide on desktop */
        margin: 0 auto !important;
    }
---

<div class="container" style="max-width: 80vw; margin: 0 auto; padding: 0 2vw 5vh 2vw; text-align: center;">

<div style="margin-top: -7vh !important; padding: 0;">

<div style="text-align: center; margin: 0; padding: 0;">
<h1 style="font-family: 'Lexend Deca', sans-serif; font-size: clamp(2rem, 5vw, 3rem); color: white; margin: 0; padding: 0;"></h1>
<p style="color: #000000; font-size: 4rem; font-weight: bold; margin: 0; padding: 0; white-space: nowrap;">Jenga Builds</p>
</div>

<div style="margin-top: 2vh !important;">
{{% box color="yellow" %}}
Above are collections of various projects related to Jenga blocks. These are from middle school and high school, but I personally really like them and find them interesting to watch again. This is more of a personal portfolio for me to come back and enjoy, but feel free to look around and see the dumb stuff.
{{% /box %}}

{{% box color="blue" %}}
↓ Below this are project videos while learning how to edit. They aren't good but they are fun in their own way. ↓
{{% /box %}}
</div>

</div>

<div class="vertical-video-stack" style="margin-top: -4vh !important; padding: 0;">
{{< youtube_grid "iL8aUmd-bHg"="Tower Fall" "4CH6rJm7hnc"="Hyperventilation" "WggrtAHOCZs"="Slo Mo Jazz Hands" >}}
</div>

</div>