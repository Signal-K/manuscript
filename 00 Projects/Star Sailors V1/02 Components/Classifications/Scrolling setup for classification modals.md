---
tags:
  - Classifications
  - Components
  - Structures
  - Star-Sailors
connie-publish: true
sticker: lucide//file-cog
---
### Changes for `CameraReceiverStation` Component

1. **Added `overflow-hidden` and `relative` to the modal container:**
    
    javascript
    
    Copy code
    
    `<div className="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50">   <div className="bg-white dark:bg-gray-800 rounded-lg w-full max-w-lg mx-auto shadow-lg overflow-hidden">`
    
2. **Added `relative` to the content area and `max-h-[80vh]` and `overflow-y-auto` for scrolling:**
    
    javascript
    
    Copy code
    
    `<div className="relative p-6 max-h-[80vh] overflow-y-auto">`
    
3. **Updated close button to position it absolutely:**
    
    javascript
    
    Copy code
    
    `<button className="btn btn-square btn-outline absolute top-2 right-2" onClick={onClose}>   ✕ </button>`
    
4. **Added `mt-4` for space between the main content and buttons:**
    
    javascript
    
    Copy code
    
    `<button   onClick={() => setShowUserImages(true)}   className="px-4 py-2 bg-green-500 text-white rounded-lg shadow-md hover:bg-green-700 mt-4" >   View my images and create a post </button>`
    
5. **Added `mt-4` for the button in the user images section:**
    
    javascript
    
    Copy code
    
    `<button   onClick={() => setShowUserImages(false)}   className="px-4 py-2 bg-red-500 text-white rounded-lg shadow-md hover:bg-red-700 mt-4" >   Back to fetched images </button>`
    

### Changes for `MeteorologyToolModal` Component

1. **Added `overflow-hidden` to the modal container:**
    
    javascript
    
    Copy code
    
    `<div className="fixed inset-0 z-50 flex items-center justify-center bg-black bg-opacity-50">   <div className="bg-white rounded-lg p-4 w-full max-w-lg mx-auto shadow-lg overflow-hidden">`
    
2. **Added `relative` to the content area and `max-h-[80vh]` and `overflow-y-auto` for scrolling:**
    
    javascript
    
    Copy code
    
    `<div className="relative p-4 max-h-[80vh] overflow-y-auto">`
    
3. **Updated close button to position it absolutely:**
    
    javascript
    
    Copy code
    
    `<button className="btn btn-square btn-outline absolute top-2 right-2" onClick={onClose}>   ✕ </button>`
    

### Summary of Changed Code for Scrolling

#### `CameraReceiverStation` Component

javascript

Copy code

`// Added overflow-hidden and relative to the modal container <div className="bg-white dark:bg-gray-800 rounded-lg w-full max-w-lg mx-auto shadow-lg overflow-hidden">      // Added relative to the content area and max-h-[80vh] and overflow-y-auto for scrolling   <div className="relative p-6 max-h-[80vh] overflow-y-auto">      // Updated close button   <button className="btn btn-square btn-outline absolute top-2 right-2" onClick={onClose}>     ✕   </button>      // Added mt-4 for space between the main content and buttons   <button     onClick={() => setShowUserImages(true)}     className="px-4 py-2 bg-green-500 text-white rounded-lg shadow-md hover:bg-green-700 mt-4"   >     View my images and create a post   </button>      // Added mt-4 for the button in the user images section   <button     onClick={() => setShowUserImages(false)}     className="px-4 py-2 bg-red-500 text-white rounded-lg shadow-md hover:bg-red-700 mt-4"   >     Back to fetched images   </button>`

#### `MeteorologyToolModal` Component

javascript

Copy code

`// Added overflow-hidden to the modal container <div className="bg-white rounded-lg p-4 w-full max-w-lg mx-auto shadow-lg overflow-hidden">      // Added relative to the content area and max-h-[80vh] and overflow-y-auto for scrolling   <div className="relative p-4 max-h-[80vh] overflow-y-auto">      // Updated close button   <button className="btn btn-square btn-outline absolute top-2 right-2" onClick={onClose}>     ✕   </button>`

### Adding Scroll Styles (if needed in CSS)

css

Copy code

`@media (max-width: 768px) {   .max-w-lg {     max-width: 90%;   } }  @media (max-width: 640px) {   .max-w-md {     max-width: 95%;   } }`


Jira:
https://signalk.atlassian.net/browse/CPW-30 