# The Book of the Runtime
The Book of the Runtime (BOTR) for the .NET Runtime.

Combined articles from the official [CoreCLR repo](https://github.com/dotnet/coreclr/tree/master/Documentation/botr) about the non-trivial internals of the .NET Runtime.
It is available in EPUB format.

The ebook is created manually by combining the articles using [pandoc](https://github.com/jgm/pandoc).
NB! Links are broken in the EPUB file.

This is the ebook conversion process:
* Number all Markdown files
* Create metadata.yaml file
* Merge all MD files, convert it to EPUB and append metadata

The command to create the EPUB file, needs to be run from `./Resources/botr`:  
```pandoc "01-README.md" $(Get-ChildItem -Filter "*.md" | Where-Object { $_.Name -ne "01-README.md" } | Sort-Object Name) -o ../../Book-of-the-Runtime.epub --resource-path="." --metadata-file=../../metadata.yaml```
