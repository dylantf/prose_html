# Repository Guidelines

## Project Structure & Module Organization

Keep library code, application/demo code, documentation, and tests in their
existing top-level areas. Put reusable APIs in library modules and keep examples
or runnable applications separate from the core implementation. Do not edit
generated reference documentation by hand; update the source comments or the
generator instead.

## Build, Test, and Development Commands

- `saga fmt <filename>`: format Saga source files before building when changing
  `.saga` files.
- `saga build`: compile the project. Run this before handing work back after
  code changes.
- `saga test`: run the fast in-process test suite after library or behavior
  changes.
- `saga docs --output ./docs/reference`: regenerate API reference docs from
  `#@` source comments when reference output needs updating.
- `nix develop`: enter the development shell on systems that use the provided
  Nix flake.

## Coding Style & Naming Conventions

Use existing Saga style: two-space indentation inside records, handlers, and
case arms; short `snake_case` function names; `PascalCase` types and variants.
Saga does not use significant whitespace for function calls, so do not break
arguments onto multiple lines unless the whole call is wrapped in parentheses.
Keep public APIs small and document them with `#@` comments when they are
intended for generated reference docs. Prefer composing ordinary functions and
effects over adding framework-specific abstractions.

- Do not make useless import aliases like `import SomeModule.Foo as Foo`. The
  `as Foo` is redundant.

## Testing Guidelines

Prefer in-process tests for pure routing, parsing, helpers, and other behavior
that does not require starting external services. Add runnable demos or
integration tests only when behavior needs manual or end-to-end exercise.

## Agent-Specific Instructions

For Saga language help, use `~/projects/saga-website/public/llms.txt` as the
guide index, or `~/projects/saga-website/public/syntax-reference.md` to
double-check surface syntax. Avoid reverting unrelated work. If Saga hits an
unexpected compiler panic or runtime panic, pause work and report it instead of
working around it; those should be fixed in the compiler.
