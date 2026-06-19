---
name: rust-idiomatic-api
description: Review Rust code for scripting-style API design and missing Rust idioms.
---

When reviewing Rust code, flag API design that looks like Python or JavaScript translated into Rust.

Look for:

- Functions with more than four parameters, especially related values that should be a struct.
- Repeated parameter groups passed through multiple layers.
- Free functions that primarily operate on one domain type and should be an `impl` method.
- `xxx_to_yyy` helpers that should be `From` or `TryFrom`.
- Boolean-heavy APIs where an enum or options struct would encode intent better.
- Stringly typed states, modes, IDs, or flags that should be enums or newtypes.
- Unnecessary `clone()` caused by poor ownership design.

Only report issues that materially affect maintainability, API clarity, or correctness.
For each finding, suggest the idiomatic Rust shape.
