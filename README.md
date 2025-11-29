# Nova Core
**Nova Core** is the foundational module of the Nova Engine and overall Nova Engine family.
It provides the essential low-level types, math utilities, and abstractions that all other Nova modules rely on.

This module focuses on **performance and consistency** while internally just cglm c++ abstraction but still adds useful things outside math and cglm.

## Features
### Math Structures (cglm-backend)
Nova Core defines modern c++ wrappers around cglm types:
- Vec2 - 2D vec
- Vec3 - 3D vec
- Vec4 - 4D vec
- Mat4 - 4x4 transformation matrix
- Quat - quaternion for rotations
- Transform - position, rotations and scale in one struct

Each wrapper provides
- Operator Overloads (`+`, `-`, `*`, `/`, indexing)
- Normalization, length, dot/cross (if added)
- Matrix/Vector transforms
- Quaternion rotation utilities
- Conversion to/from raw cglm types
- Automatic alignment where required (e.g., `alignas(16)`)
cglm remains the underlying engine ensuring:
- SIMD-friendly operations
- Zero cost conversions
- Maximum Performance and stability

## Purpose
Nova Core exists to
1. **Define stable shared data structures** for the entire Nova Engine
2. **Avoid math duplication** between modules like Nova Graphics, Nova Vulkan Layer, Nova Physics,..
3. **Provide a clean C++ interface** on top of cglm's C API
4. **Ensure high-performance math** through C-level optimizations
5. **Serve as minimal dependency layer** for all higher modules.
Everything in Nova Core is designed to be:
- Reusable
- Efficient
- Easy to read
- Engine-agnostic
No high-level rendering or scene logic lives here.

## Used By
Modules depending on Nova Core include:
- NGL - Nova Graphics Layer
- NVL - Nova Vulkan Layer
- NGR - Nova Graphics Renderer
- Nova Physics
- Nova Scene System
- Nova Editor
- And any custom modules using shared math types

## Special thanks
- [cglm](https://github.com/recp/cglm?tab=MIT-1-ov-file) - High performance Graphics Math (MIT Licensed)
- [fmtlib](https://github.com/fmtlib/fmt) - Fast & Modern formatting Library



Note: some of these libraries may not be in the code, but will be in the future.