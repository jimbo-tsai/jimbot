---
categories: ["content", "paige"]
date: "2025-10-19T12:12:08-05:00"
title: "Rose"
weight: 50
paige:
  style: |
    #paige-collections, #paige-metadata, #paige-sections, #paige-pages { display: none; }

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
We do not have much connection, you and I. Still, this encounter feels special. I hope you won’t mind if I think of you as a friend.
{{< /slideshow >}}
