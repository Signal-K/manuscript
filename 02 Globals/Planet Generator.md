---
tags:
  - Components
  - Generator
  - Classifications
path: "`app/(anomalies)/(planets)/generated.tsx` - SGV2-164"
Jira: 
sticker: lucide//code-2
---
Scope:
1. Show generated planet based on user's classifications & global classifications
2. Link & postcard view of all relevant/child classifications

# Onboarding
1. Shows the first two contributions the user makes - initial transit event (confirmation) and the rover photo (which generates the mineral deposit).

# Chapter 1
[[01 Chapter 1]]
1. Additional classifications will have been made (see [[Timeline]]), so we'll need to show those
2. We'll need to re-work the "completion"/image calculation as the number of available classification [options] will have increased dramatically
3. Let's point to some objects of interest (arranged by classification type & structure), just some arrows coming out of [css -> on top of] the image?