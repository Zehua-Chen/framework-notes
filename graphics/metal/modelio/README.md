# Overview

`ModelIO` provides tools to load and process models/scenes

- `MDLAsset`: asset loaded retrieved from a url (ex. `.obj`, `.usd`)
  - Allocators
  - Descriptors
  - Import, export
  - Children (`MDLObject`)
  - URL
- `MDObject`: entities in an asset; can be recursive
  - Name
  - Components (ex. behaviors, transforms)
  - Transform
  - Bounding box
  - Parent
  - Children (`MDLObject`)
  - Variants: `MDLMesh`, `MDLLight`, `MDLCamera`
- `MDLMesh`
  - Vertex buffers (`MDLMeshBuffer`)
  - Submeshes (`MDLSubmesh`): contain triangle or polygon indices and share data
    in vertex buffer
  - Descriptors (`MDLVertexDescriptor`)
  - **Helpers**
    - Generators
    - Modifiers (ex. create normals)
    - Bakers
  - **Operations**
    - Normal smoothing
    - Subdivision
- `MDLLight`
- `MDLCamera`
- `MDLMeshBuffer`
  - Data
  - Length
  - Allocator
- `MDLVertexDescriptor`
  - Name
  - Attributes
  - Layout
- `MDLSubmesh`
  - Name
  - Index buffer
  - Geometry type
  - Material (`MDLMaterial`)
- `MDLMaterial`
  - Name
  - Properties
  - Scattering Function (ex. blinn-phong, physically-based)
  - Base Material

# File Formats

[Asset File Types](https://developer.apple.com/documentation/modelio/mdlasset/asset_file_types)
