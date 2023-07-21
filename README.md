# custom-solution-template
JSON and instructions for creating a custom solutions template inside Visual Studio.

Microsoft tutorials can be found at https://learn.microsoft.com/en-us/dotnet/core/tutorials/cli-templates-create-item-template

Reference for JSON template can be found at https://github.com/dotnet/templating/wiki/Reference-for-template.json

QUICK STEPS: 

1) Create a folder called ".template.config" inside the same solutions folder you wish to create as a template.
2) Add a filed named "template.json" to the ".template.config" folder.
3) Customize the JSON template accordingly.

EXAMPLE:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Justin R. Buchanan",
  "classifications": [ "ASP.NET", "Website", "Solution" ],
  "identity": "Csg.Templates.AspNetCore.Website",
  "name": "CSG ASP.NET Core Website Solution",
  "sourceName": "Skeleton",
  "preferNameDirectory": true,
  "shortName": "csgaspnetweb",
  "symbols": {
    "title": {
      "type": "parameter",
      "datatype": "string",
      "replaces": "PROJECT-TITLE",
      "isRequired": true,
      "description": "The display name used in assembly info and as the default website title"
    }
  },
  "sources": [
    {
      "modifiers": [
        {
          "exclude": [
            "\*\*/.git/\*\*",
            "\*\*/.vs/\*\*"
          ]
        }
      ]
    }
  ]
}
```
