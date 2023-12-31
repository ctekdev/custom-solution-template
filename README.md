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
  "author": "CTekDev",
  "classifications": [ "ASP.NET", "API", "SOLUTION" ],
  "identity": "CTekDev.AspNet.API.JWT",
  "name": "CTekDev API & JWT",
  "sourceName": "CTekDev",
  "preferNameDirectory": true,
  "shortName": "ctekapijwt",
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

4) To install - navigate inside the solutions folder and run

```
dotnet new install .\
```
5) The solution will be installed as a project template from which you can access from inside the VS IDE when creating a new project or from the dotnet cli such as

```
dotnet new ctekapijwt -title "CTeckDev JWT API" -output CTekDev
```

NOTE
If looking to install as a template package refer to https://learn.microsoft.com/en-us/dotnet/core/tutorials/cli-templates-create-item-template for similar steps. 

TEMPLATE.JSON EXPLANATION

The symbols attribute allows you specify the project title when using dotnet cli, as depicted above. Otherwise, the project title defaults to the name of the solution / project the template was generated from. By providing the soureName property, you can replace any namespace etc. where that property is being used.  
