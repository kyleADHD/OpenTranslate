
# OpenTranslate

OpenTranslate is powered by an opensource translation engine, giving you great translations.
However it has a 5000 character limit per a day, per IP. 
This can be used asynchronously.

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

string json = await engine.GetTranslation("Hello, May the forc e be with you.", "en", "es");

Results results = JsonSerializer.Deserialize<Results>(json);

Console.Write("Your Translation: " + results.Translation + Environment.NewLine +
"Match Accuracy: " + results.Percentage);

internal class Results
{
  public string Translation {get;set;}
  public string Percentage {get;set;}
  public string LanguageFrom {get;set;}
  public string LanguageFrom {get;set;}
}
```


## License

[MIT](https://choosealicense.com/licenses/mit/)


## Support

For support, email jadenyukinum1@gmail.com.

