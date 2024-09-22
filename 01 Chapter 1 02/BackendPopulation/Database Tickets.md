---
sticker: lucide//joystick
tags:
  - Tickets
  - Database
  - Chapters
  - Chapter-1
  - Chapter-2
  - Configuration
---
[[Configurations]]
1. How do we organise #Surveyor results from the user?
2. Custom/additional inputs for #PostForm -> e.g. `t0` for #Anomalies 

Create a component in the #Generator that takes the average value from each #Classifications #Configuration point (e.g. `t0`). This helps create a culture of repetition and looking at different data modes. This could perhaps remove the need for interactive Jupyter notebooks (for now) because we could create #data-dumps using a flask api that generates the lightkurve images...maybe we also show the code that goes into them (rendered dynamically) and an "open in Jupyter" button?