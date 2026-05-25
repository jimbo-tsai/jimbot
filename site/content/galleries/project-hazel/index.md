---
categories: ["content", "paige"]
date: "2022-01-19T11:12:09-05:00"
title: "Hazel"
weight: 21

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

---

<style>
  /* 1. Hide the title elements */
  main h1, 
  .paige-header h1, 
  #paige-metadata h1, 
  .display-1, .display-2, .display-3, .display-4, .display-5 { 
    display: none !important; 
  }

  /* 2. Disregard layout restrictions and force center the slideshow wrap */
  .paige-page, main > div {
    position: absolute !important;
    top: 50% !important;
    left: 50% !important;
    transform: translate(-50%, -50%) !important;
    width: 100% !important;
    max-width: 100vw !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  /* 3. Ensure the main layout container scales correctly to prevent scroll overlaps */
  main {
    min-height: 80vh !important;
    position: relative !important;
  }
</style>

{{< slideshow images="*.jpg" >}}
A hazel-tinted look at life in Chicago.
{{< /slideshow >}}