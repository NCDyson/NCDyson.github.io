---
published: false
categories: projects
---

sCCS, or StudioCCS is the early stages of a program that I hope will become a fully featured toolkit for working with CC2's CCS files.

Currently, it's features are limted to Model Viewing and dumping.

There are two viewport modes in sCCS, the Preview Viewport, and the Scene Viewport.
The Preview Viewport contains a tree view that shows all of the currently loaded CCS files.
The following sub items are currently displayed for loaded CCS files:
- Clumps(Skeletons)  
 A list of Object(Bone) Nodes
 - Objects(Bones)  
 A Bone like object containing optional references to Model and Shadow Model  
   - Models  
  	Meshes that may contain zero or more submeshs.  
    There are 4 main types of Mesh type
     - Rigid  
      No Deformable parts, mainly used for static things like scenary  
     - Deformable  
      Contains 0 or more Sub Meshes with vertices that are rigidly weighted to a single bone and share no triangles with vertices that are weighted to multiple bones  
      followed by one Sub Mesh that contains vertices that are weighted to multiple bones, or share triangles with multi-weighted vertices  
     - Shadow  
      Shadow Planes for projecting dynamic shadows onto  
     - Morph Target  
      Rigid Sub Meshes used for Morph Target Animation
     
 Clicking on a Clump in the Preview Mode Tree will list render the clump and all of it's children.  
 Bones are only visualized when the Bone Editor for that clump is open.  
 
 Clicking on an Object will Render the Sub Meshes for that Object.  
 
 Clicking on a Model will Render the Sub Meshes for that Model.  
 
 Due to the format of the files, clicking on an child Object or Model for a given clump may not render anything. This behavior may be fixed at a later time.  
 
- Materials  
 Materials contain a texture assignment, an alpha value, and texture cooridnate offsets. In Generation 2 more parameters were added, but as of now they are ignored until their purpose can be confirmed.  
 
 Currently, clicking on a Material in the Preview Tree does nothing.

- Textures:  
 There are 2 known types commonly used in Generation 1 files:  
  - 4bit Indexed Color  
  - 8bit Indexed Color  
  
  An additional type has been spotted in Generation 2 CCS Files:  
  - 32bit RGBA Color  
  
  Generation 3 added support for at least two new texture types  
  - DXT1
  - DXT5
  
  .hack//Link also supports Non-Power of 2 textures, however, these are usually Swizzled, and are currently unsupported. I've only seen these inside of the Comic Cutscene files anyways.  
  
  Currently, clicking on a texture in the Preview Mode Tree will render the texture onto a two dimensional plane.  
  
- Hit Meshes  
 Hit meshes contain collision meshes. Each Sub Mesh may have a color assigned to it for shading with baked lighting.  
Currently, clicking on a Hit Mesh or a Sub Mesh in the Preview Mode Tree does nothing. This will be fixed at a later date.










