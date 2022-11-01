
# OpenTranslate

OpenTranslate is powered by an opensource translation engine, giving you great translations.
However we do have a 500 character limit per a translation we are currently still working on bulk translations per use. 
This can be used synchronously or asynchronously.


## Optimizations

We have added better error handling to the package and fixed up some bugs that we found during testing which caused empty json strings to be returned.
## Package Dependencies

| Package             | Version                                                              |
| ----------------- | ------------------------------------------------------------------ |
| Newtonsoft.Json | 13.0.1 |

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
  public string Percentage {get;set;}
  public string LanguageFrom {get;set;}
  public string LanguageTo {get;set;}
}
```


## Roadmap

- Add OCR image and document translations.
(currently we have started development on this.)

- Add code and performance optimisation.


## License

[MIT](https://choosealicense.com/licenses/mit/)


## Support

For support, email WebsiterzTech@gmail.com.

