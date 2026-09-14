# Semantic WebView2 Module

This module contains the Microsoft WebView2 SDK imported from the vcpkg `webview2:x64-windows` package.

## Contents

- `semantic/` — structured Semantic projections of the supported WebView2/WIL headers
- `source/` — original headers, import libraries, DLLs, WinRT metadata and CMake metadata
- `licenses/` — license material recorded by the importer
- `semantic-webview2.smod` — module manifest

## Use from Semantic

The `.se` and `.spz` files expose the parsed declarations and types to the Semantic module resolver. The native WebView2 implementation remains an external Windows ABI dependency and requires the corresponding files from `source/x64-windows` when producing a native executable:

- `include/` for declarations
- `lib/` or `debug/lib/` for linking
- `bin/WebView2Loader.dll` and `bin/Microsoft.Web.WebView2.Core.dll` at runtime

The imported Semantic projections do not replace the Microsoft WebView2 runtime. They provide the canonical module representation and preserve the native ABI boundary.

Package: `webview2:x64-windows`
Target: Windows x64
