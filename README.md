
# OpenTranslate

OpenTranslate is powered by an opensource translation engine, giving you great translations.
However we do have a 500 character limit per a translation  we are currently still working on bulk translations per use.
You are also currently limited to 5000 characters per day per ip - we are working on getting rid of all limits.
This can be used asynchronously.


## Optimizations

We have added better error handling to the package and fixed up some bugs that we found during testing which caused empty json strings to be returned
We have also added ocr document translations.
## Package Dependencies

| Package             | Version                                                              |
| ----------------- | ------------------------------------------------------------------ |
| Newtonsoft.Json | 13.0.1 |
| IronOcr | 2022.11.10109 |
| IronOcr.MacOs | 2022.11.10109 |

## Usage/Examples
GetTranslation(Sentence or Phrase, laguage from, language to);

Languages need to be specified in ISO 639-1 format like below:
```cs
using OpenTranslate;

var engine = new OpenTranslateClient();

string json = await engine.GetTranslation("Hello, May the force be with you.", "en", "es");

Results results = JsonSerializer.Deserialize<Results>(json);

Console.Write("Your Translation: " + results.Translation + Environment.NewLine +
"Match Accuracy: " + results.Percentage);

internal class Results
{
  public string Translation {get;set;}
  public string MatchPercentage {get;set;}
  public string LanguageFrom {get;set;}
  public string LanguageTo {get;set;}
}
```
GetDocumentTraslation(Document Path, isoLanguageFrom, isoLanguageTo)

Languages need to be specified in ISO 639-1 format like below:
```cs
using OpenTranslate;

var engine = new OpenTranslateClient();

string json = await engine.GetDocumentTraslation("doc.pdf", "en", "es");

Results results = JsonSerializer.Deserialize<Results>(json);

Console.Write("Your Translation: " + results.Translation + Environment.NewLine +
"Match Accuracy: " + results.Percentage);

internal class Results
{
  public string Translation {get;set;}
  public string MatchPercentage {get;set;}
  public string LanguageFrom {get;set;}
  public string LanguageTo {get;set;}
}
```


## Roadmap

- Add OCR image translations.(currently we have started development on this.)
- Add code and performance optimisation.
- Remove all usage limits to avoid limiting the free opensource product.


## License

[MIT](https://choosealicense.com/licenses/mit/)


## Support

For support, email WebsiterzTech@gmail.com.

