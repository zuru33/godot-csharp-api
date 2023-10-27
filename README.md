# Godot C# API

Unofficial web version of Godot 4.1's C# API documentation (https://zuru33.github.io/godot-csharp-api/).

## How to use this repository

1. Install [DocFX](https://dotnet.github.io/docfx/).
    1. I used version 2.70.3+3968fc5e92ebc2e4a2d97df0105000af2ec7eb82. If you use future versions, you may need to update `templates\godot\styles\docfx.js` and re-add the `&& !this[0].classList.contains('navbar-brand')` check.
1. Run `git submodule update --init --recursive` to download the darkfx template.
1. Copy the .dll files from `Godot<version>\GodotSharp\Api\Debug` to `src/<version>/`
1. Add the corresponding **metadata** entry in the [`docfx.json` file](./docfx.json#L3-L12)
1. Add the corresponding **build** entry in the [`docfx.json` file](./docfx.json#L16-L20)
1. Add the corresponding link in the [`toc.yml` file](./toc.yml#L3-L4)
1. Run `docfx metadata`
1. Run `docfx build`
    1. I had to run `docfx build` multiple times to get the table of contents to generate correctly. The second time I changed docfx.json > templates to just "default", and it built the table of contents correctly. Then I restored the templates that were there and rebuilt a 3rd time.

The whole website should now be built under `docs/`. You can preview it locally using `docfx serve docs/`. The documentation logo is from [Godot Design](https://github.com/godotengine/godot-design/).

## Older Godot versions

Some older Godot versions have git tags. To access an older version of the API:
1. git clone this repo
1. git checkout &lt;specific verson tag&gt;
1. Install docfx
1. `docfx serve docs/`