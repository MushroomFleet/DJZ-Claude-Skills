---
name: TiledSVG
description: Create complex, detailed SVG graphics through tiled grid decomposition. Use when generating characters, scenes, objects, illustrations, or any detailed vector artwork. Decomposes images into grid tiles, designs each tile independently with layered shapes, then assembles into cohesive output. Triggers on requests for detailed SVG art, character design, complex illustrations, scene composition, or when standard single-pass SVG approaches produce insufficient detail.
---

# TiledSVG: Tiled Grid SVG Creation

Create complex SVG graphics by decomposing the canvas into a tile grid, designing each tile with focused detail, then assembling into a unified image.

## Core Method

1. **Plan** - Define canvas size, grid density, and map subject to tiles
2. **Define** - Create color palette with gradients/patterns in `<defs>`
3. **Build** - Construct each tile as a `<g>` group with local coordinates
4. **Layer** - Add depth within tiles: shadows → base → details → highlights
5. **Assemble** - Position tiles with `transform="translate(x, y)"`

## Grid Selection

| Complexity | Grid | Tiles | Use Case |
|------------|------|-------|----------|
| Simple | 4×4 | 16 | Icons, symbols |
| Medium | 6×6 | 36 | Simple characters, objects |
| Detailed | 8×8 | 64 | Scenes, detailed characters |
| Complex | 9×9+ | 81+ | Full illustrations, landscapes |

Formula: `tile_size = canvas_size / grid_count`

## Step 1: Reference Mapping

Map subject onto grid with annotations:

```
House Scene (9×9):
┌───┬───┬───┬───┬───┬───┬───┬───┬───┐
│ S │ S │ S │ S │ S │ S │ S │ ☀ │ S │  S=Sky
├───┼───┼───┼───┼───┼───┼───┼───┼───┤
│ ☁ │ S │ S │ S │ S │ S │ S │ S │ ☁ │  ☁=Cloud
├───┼───┼───┼───┼───┼───┼───┼───┼───┤
│ S │ S │ C │ R │ R │ R │ R │ S │ S │  C=Chimney R=Roof
├───┼───┼───┼───┼───┼───┼───┼───┼───┤
│ S │ T │ W │ H │ H │ H │ W │ T │ S │  T=Tree W=Window
├───┼───┼───┼───┼───┼───┼───┼───┼───┤
│ G │ T │ H │ D │ D │ D │ H │ T │ G │  D=Door H=House
├───┼───┼───┼───┼───┼───┼───┼───┼───┤
│ G │ G │ G │ P │ P │ P │ G │ G │ G │  G=Grass P=Path
├───┼───┼───┼───┼───┼───┼───┼───┼───┤
│ F │ G │ G │ P │ P │ P │ G │ G │ F │  F=Flowers
├───┼───┼───┼───┼───┼───┼───┼───┼───┤
│ G │ F │ G │ P │ P │ P │ G │ F │ G │
├───┼───┼───┼───┼───┼───┼───┼───┼───┤
│ G │ G │ G │ P │ P │ P │ G │ G │ G │
└───┴───┴───┴───┴───┴───┴───┴───┴───┘
```

## Step 2: Color Palette in Defs

Define all gradients, patterns, and filters before drawing:

```xml
<defs>
  <!-- Semantic grouping -->
  <linearGradient id="sky-gradient" x1="0%" y1="0%" x2="0%" y2="100%">
    <stop offset="0%" stop-color="#0d47a1"/>
    <stop offset="60%" stop-color="#64b5f6"/>
    <stop offset="100%" stop-color="#e3f2fd"/>
  </linearGradient>
  
  <radialGradient id="sun-core" cx="50%" cy="50%" r="50%">
    <stop offset="0%" stop-color="#ffffff"/>
    <stop offset="70%" stop-color="#ffeb3b"/>
    <stop offset="100%" stop-color="#ffc107"/>
  </radialGradient>
  
  <linearGradient id="foliage-main" .../>
  <linearGradient id="trunk-main" .../>
  <linearGradient id="wall-main" .../>
  <linearGradient id="roof-main" .../>
  
  <pattern id="grass-blades" width="12" height="12" patternUnits="userSpaceOnUse">
    <path d="M 2,12 Q 2,8 3,6" stroke="#2e7d32" stroke-width="1.5" fill="none"/>
    <path d="M 6,12 Q 5,7 7,4" stroke="#388e3c" stroke-width="1" fill="none"/>
  </pattern>
</defs>
```

## Step 3: Tile Construction

Each tile is a `<g>` group positioned by transform. Use local coordinates (0-100 for 100px tiles):

```xml
<!-- Row-Column naming: tile-{row}-{col} -->
<!-- Position formula: translate(col * tileSize, row * tileSize) -->

<g id="tile-3-3" transform="translate(300, 300)">
  <!-- Layer 1: Base shape -->
  <rect width="100" height="100" fill="url(#wall-main)"/>
  
  <!-- Layer 2: Window frame -->
  <rect x="15" y="15" width="70" height="70" fill="#5d4037"/>
  
  <!-- Layer 3: Window glass -->
  <rect x="20" y="20" width="60" height="60" fill="url(#window-glass)"/>
  
  <!-- Layer 4: Window cross -->
  <rect x="48" y="20" width="4" height="60" fill="#eceff1"/>
  <rect x="20" y="48" width="60" height="4" fill="#eceff1"/>
  
  <!-- Layer 5: Reflection highlight -->
  <rect x="22" y="22" width="24" height="24" fill="#fff" opacity="0.3"/>
</g>
```

## Step 4: Layering Order

Within each tile, build depth back-to-front:

1. **Background/Base** - Fill shapes, base colors
2. **Shadows** - Dark shapes with low opacity
3. **Main elements** - Primary subject shapes
4. **Details** - Texture lines, patterns, small elements
5. **Highlights** - White/light shapes with transparency

```xml
<g id="tile-tree-foliage" transform="translate(100, 300)">
  <!-- 1. Shadow mass -->
  <ellipse cx="50" cy="70" rx="50" ry="40" fill="#2e7d32" opacity="0.4"/>
  
  <!-- 2. Main foliage -->
  <ellipse cx="50" cy="55" rx="48" ry="38" fill="url(#foliage-main)"/>
  <ellipse cx="30" cy="45" rx="35" ry="30" fill="url(#foliage-main)"/>
  <ellipse cx="70" cy="50" rx="30" ry="25" fill="#4caf50"/>
  
  <!-- 3. Highlight spots -->
  <ellipse cx="25" cy="38" rx="12" ry="10" fill="#a5d6a7" opacity="0.6"/>
  <ellipse cx="60" cy="35" rx="10" ry="8" fill="#c8e6c9" opacity="0.5"/>
</g>
```

## Step 5: Cross-Tile Continuity

Elements spanning multiple tiles must align at edges:

```xml
<!-- Path crossing tiles 5-3, 5-4, 5-5 -->

<!-- tile-5-3: Path exits right -->
<g id="tile-5-3" transform="translate(300, 500)">
  <path d="M 30,0 Q 25,50 35,100" fill="url(#path-main)"/>
  <rect x="30" y="0" width="70" height="100" fill="url(#path-main)"/>
</g>

<!-- tile-5-4: Path continues full width -->
<g id="tile-5-4" transform="translate(400, 500)">
  <rect x="0" y="0" width="100" height="100" fill="url(#path-main)"/>
</g>

<!-- tile-5-5: Path enters left -->
<g id="tile-5-5" transform="translate(500, 500)">
  <rect x="0" y="0" width="70" height="100" fill="url(#path-main)"/>
  <path d="M 70,0 Q 75,50 65,100" fill="url(#path-main)"/>
</g>
```

## SVG Structure Template

```xml
<svg viewBox="0 0 900 900" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <!-- All gradients, patterns, filters -->
  </defs>

  <!-- Background -->
  <rect width="900" height="900" fill="url(#sky-gradient)"/>

  <!-- Tiles by row -->
  <g id="row-0">
    <g id="tile-0-0" transform="translate(0, 0)">...</g>
    <g id="tile-0-1" transform="translate(100, 0)">...</g>
    <!-- ... -->
  </g>
  
  <g id="row-1">
    <g id="tile-1-0" transform="translate(0, 100)">...</g>
    <!-- ... -->
  </g>
  
  <!-- Continue for all rows -->
</svg>
```

## Detail Techniques

### Organic Shapes (Foliage, Clouds)
Stack multiple ellipses with varying positions and opacities:
```xml
<ellipse cx="50" cy="50" rx="40" ry="30" fill="#4caf50"/>
<ellipse cx="30" cy="40" rx="30" ry="25" fill="#66bb6a"/>
<ellipse cx="70" cy="45" rx="25" ry="20" fill="#81c784"/>
```

### Texture Overlays
Apply patterns with low opacity over base fills:
```xml
<rect width="100" height="100" fill="url(#hill-gradient)"/>
<rect width="100" height="100" fill="url(#grass-blades)" opacity="0.4"/>
```

### Architectural Details
Use rectangles with inset shadows for depth:
```xml
<!-- Door panel -->
<rect x="10" y="15" width="35" height="30" fill="url(#door-panel)" rx="2"/>
<!-- Inset shadow -->
<rect x="13" y="18" width="29" height="24" fill="#4e342e"/>
```

### Small Details (Wildlife, Flowers)
Group related shapes with local transforms:
```xml
<!-- Butterfly -->
<g transform="translate(60, 40) rotate(-15)">
  <ellipse cx="0" cy="0" rx="2" ry="7" fill="#5d4037"/>
  <ellipse cx="-10" cy="-4" rx="10" ry="7" fill="#ff9800"/>
  <ellipse cx="10" cy="-4" rx="10" ry="7" fill="#ff9800"/>
</g>
```

## Iteration Process

1. **Rough Pass** - Block in major shapes per tile
2. **Structure Pass** - Add architectural/structural elements
3. **Detail Pass** - Internal details, textures, small elements
4. **Edge Pass** - Verify cross-tile alignment
5. **Polish Pass** - Highlights, shadows, final adjustments

## Common Gradient Types

| Element | Gradient Type | Direction |
|---------|--------------|-----------|
| Sky | Linear | Top to bottom |
| Sun/Lights | Radial | Center out |
| Walls | Linear | Left to right or top to bottom |
| Foliage | Radial | Upper-center out |
| Ground | Linear | Top to bottom |
| Cylindrical (trunks) | Linear | Left to right |
