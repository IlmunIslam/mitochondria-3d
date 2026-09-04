# Mitochondrion — 3D Biological Model

A scientifically-structured 3D model of a **mitochondrion**, built in Blender for
educational and scientific-visualization use. The model is organized around the
organelle's real anatomy rather than as a single undifferentiated mesh, so the
outer membrane, inner membrane, and matrix can be shaded, sectioned, or animated
independently.

## Tech stack

- **Authoring:** Blender **4.0.2**
- **Workflow:** organic modelling and sculpting, subdivision surfaces, procedural
  shader node trees
- **Interchange:** FBX export for use in real-time engines (Unity)

## Structure

The scene separates the organelle into distinct membrane and matrix datablocks:

| Datablock | Anatomical role |
|---|---|
| `Mitochondria Exterior` | Outer mitochondrial membrane — the smooth outer envelope |
| `Mitochondria Interior` | Inner membrane, folded into the cristae that carry the electron transport chain |
| `ME Liquid` | Intermembrane space — the compartment between outer and inner membranes |
| `MI Liquid` | Mitochondrial matrix — the innermost compartment enclosed by the cristae |

Exterior and interior surfaces carry **separate materials**, so the inner membrane
remains visible and distinguishable in cutaway and cross-section views — the
presentation that actually teaches the structure.

## Why the separation matters

A mitochondrion is not visually interesting from the outside; its function lives in
the **cristae**, the folds of the inner membrane that provide the surface area for
ATP synthesis. Modelling the membranes and compartments as separate objects means a
cross-section can be taken without re-authoring geometry, and each compartment can
be labelled, coloured, or faded independently in a teaching animation.

## Repository contents

| Path | Description |
|---|---|
| `source/Mitochondria.blend` | Blender source file — full modifier stack, materials, and shader node trees |
| `exports/Mitochondria.fbx` | Baked FBX export for real-time engine import |

## Using it

**In Blender:** open `source/Mitochondria.blend` with Blender 4.0 or newer.

**In Unity or another engine:** import `exports/Mitochondria.fbx`. Note that FBX
carries geometry, UVs, and normals but **not** Blender's procedural node-based
materials — those need to be rebuilt as engine materials, or baked to textures from
the source file first.

No Git LFS required.

## Context

Produced as part of biological / medical visualization work at Hospital IT
(Terminal, Rangpur), alongside interactive stomach and colon endoscopy simulations.

> **Disclaimer:** For **educational and visualization purposes only**. Not a medical
> device, and not intended for clinical, diagnostic, or treatment use.

## License

Released under the **MIT License** — see [LICENSE](LICENSE).
