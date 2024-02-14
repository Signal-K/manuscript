---
title: Alchemy Canvas Planning
tags:
  - Star-Sailors
  - Building
  - Gameplay
  - Planning
---
A page that will go over some brief plans for the minigame components, see [![](https://signalk.atlassian.net/rest/api/2/universal_avatar/view/type/issuetype/avatar/10318)GP-14: Test out alchemy-type crafting minigameIN PROGRESS](https://signalk.atlassian.net/browse/GP-14)

Jira: https://signalk.atlassian.net/wiki/x/A4Au 

- [Alchemy](https://signalk.atlassian.net/wiki/spaces/AGP/pages/3047427/Game+canvases#Alchemy)
    - [Database pipelines](https://signalk.atlassian.net/wiki/spaces/AGP/pages/3047427/Game+canvases#Database-pipelines)

# Alchemy

Current raw materials:

1. Coal
    
2. Silicates
    
3. Iron
    
4. Nickel
    
5. Alloy
    
6. Fuel
    
7. Copper
    
8. Chromium
    
9. Water
    

I think we can add the following:

|   |   |   |
|---|---|---|
|**Material**|**State of matter**|**Extraction method**|
|Coal|Solid (Ore)||
|Silicates|Solid||
|Iron|Solid (Ore)||
|Nickel|Solid (Ore)||
|Alloy|Solid (Ore)||
|Fuel|Liquid||
|Copper|Solid (Ore)||
|Chromium|Solid (Alloy)||
|Water|Liquid/Solid (Ice)||
|Basalt|Solid (rock formations)||
|Carbon Dioxide|Gas (atmosphere), solid (polar ice caps)||
|Methane|Gas (atmosphere), solid (subsurface ice deposits)||
|Sulfur|Solid (in volcanic areas, ore in sulfates)||
|Hematite|Solid (ore, or concentration)||
|Aluminum|Solid||
|Titanium|Solid||
|Oxygen|Gas (atmosphere)||
|Nitrogen|Gas (atmosphere)||
|Phosphorus|Solid||
|Sodium|Solid (salt)||
|Potassium|Solid (salt/minerals)||
|Calcium|Solid (ore/carbonate, subsurface)||
|Magnesium|Solid||
|Hydrogen|Gas (atmosphere)||
|Helium|Gas (atmosphere)||
|Argon|Gas (atmosphere)||
|Xenon|Gas (atmosphere)||
|Perchlorates|Solid (varies, on surface)||
|Regolith|Solid (surface)||

## Database pipelines

- Read from `inventoryUSERS`
    
- Provide the user with a list of items they currently have available (let’s not worry about where items are located or any other discriminators for now)
    
- Make a log of the raw materials they use up, and at the end of a “transaction/play session”, if they confirm the full transaction, deduct those raw materials and reward the new ones (use cookies for saving incomplete transactions)