# TypefaceUtil

![CI](https://github.com/wieslawsoltes/TypefaceUtil/workflows/CI/badge.svg)

[![NuGet](https://img.shields.io/nuget/v/TypefaceUtil.OpenType.svg)](https://www.nuget.org/packages/TypefaceUtil.OpenType)
[![NuGet](https://img.shields.io/nuget/dt/TypefaceUtil.OpenType.svg)](https://www.nuget.org/packages/TypefaceUtil.OpenType)

[![GitHub release](https://img.shields.io/github/release/wieslawsoltes/TypefaceUtil.svg)](https://github.com/wieslawsoltes/TypefaceUtil)
[![Github All Releases](https://img.shields.io/github/downloads/wieslawsoltes/TypefaceUtil/total.svg)](https://github.com/wieslawsoltes/TypefaceUtil)
[![Github Releases](https://img.shields.io/github/downloads/wieslawsoltes/TypefaceUtil/latest/total.svg)](https://github.com/wieslawsoltes/TypefaceUtil)

An OpenType typeface utilities.

## About

TypefaceUtil is a set of OpenType typeface utilities.
Currently supported are `cmap` table format parser for `character to glyph index mapping`, 
generation of character `png` map, `svg` and `xaml` export for glyphs.

## Usage

```
TypefaceUtil:
  An OpenType typeface utilities.

Usage:
  TypefaceUtil [options]

Options:
  -f, --inputFiles <inputfiles>              The relative or absolute path to the input files
  -d, --inputDirectory <inputdirectory>      The relative or absolute path to the input directory
  -p, --pattern <pattern>                    The search string to match against the names of files in the input directory [default: *.ttf]
  --fontFamily <fontfamily>                  The input font family
  -o, --outputDirectory <outputdirectory>    The relative or absolute path to the output directory
  --printFontFamilies                        Print available font families
  --printCharacterMaps                       Print character maps info
  --png, --pngExport                         Export text as Png
  --pngTextSize <pngtextsize>                Png text size [default: 20]
  --pngCellSize <pngcellsize>                Png cell size [default: 40]
  --pngColumns <pngcolumns>                  Png number of columns [default: 20]
  --svg, --svgExport                         Export text as Svg
  --svgTextSize <svgtextsize>                Svg text size [default: 16]
  --svgPathFill <svgpathfill>                Svg path fill [default: black]
  --xaml, --xamlExport                       Export text as Xaml
  --xamlTextSize <xamltextsize>              Xaml text size [default: 16]
  --xamlBrush <xamlbrush>                    Xaml brush [default: Black]
  --quiet                                    Set verbosity level to quiet
  --debug                                    Set verbosity level to debug
  --version                                  Show version information
  -?, -h, --help                             Show help and usage information
```

```
TypefaceUtil -h
```
```
TypefaceUtil --pngExport -f segoeui.ttf
TypefaceUtil --pngExport --fontFamily "Segoe UI"
```
```
TypefaceUtil --svgExport -f seguisym.ttf
TypefaceUtil --svgExport --fontFamily "Segoe UI Symbol"
```
```
TypefaceUtil --xamlExport -f calibri.ttf
TypefaceUtil --xamlExport --fontFamily "Calibri"
```

```
TypefaceUtil -d C:\Windows\Fonts -o export --png --svg --xaml
```

## Testing

```
dotnet run -c Release -- --help
dotnet run -c Release -- --printFontFamilies
dotnet run -c Release -- --debug -f ../../../ttf/segoeui.ttf
dotnet run -c Release -- --debug --fontFamily "system"
dotnet run -c Release -- -d ../../../ttf/ --svg -o export
dotnet run -c Release -- -d ../../../ttf/ --xaml -o export
dotnet run -c Release -- -d ../../../ttf/ --png -o export
dotnet run -c Release -- --png --svg --xaml -d ../../../ttf/ --pngColumns 20 --pngTextSize 50 --pngCellSize 70 --svgTextSize 22 --svgPathFill "#000000" --xamlTextSize 22 --xamlBrush "#FF000000"
dotnet run -c Release -- --png --svg --xaml --fontFamily "system"
dotnet run -c Release -- --png --svg --xaml -f ../../../ttf/segoeui.ttf
dotnet run -c Release -- --png --svg --xaml -f ../../../ttf/seguisym.ttf
dotnet run -c Release -- --png --svg --xaml -f ../../../ttf/calibri.ttf
dotnet run -c Release -- --png --svg --xaml -f ../../../ttf/segoeui.ttf --pngColumns 20 --pngTextSize 50 --pngCellSize 70
dotnet run -c Release -- --png --svg --xaml --fontFamily "Segoe UI"
dotnet run -c Release -- --png --svg --xaml --fontFamily "Segoe UI Symbol"
dotnet run -c Release -- --png --svg --xaml --fontFamily "Calibri"
```

## References

* https://docs.microsoft.com/en-us/typography/opentype/spec/cmap
* https://docs.microsoft.com/en-us/dotnet/api/skiasharp.sktypeface?view=skiasharp-1.68.1

## License

TypefaceUtil is licensed under the [MIT license](LICENSE.TXT).
