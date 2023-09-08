<div align="center">

<img src="https://github.com/seanhlewis/translatelove/assets/96705270/6f7b9adc-321e-4d69-bd24-e76e7d6b355c" width="800" />

# A Free and Open Source Machine Translation API

</div>

[Translate.love](https://translate.love) is a free and open source machine translation API developed for translating any variety of text and documents in over 30 different languages. It provides a free-to-use API for real-time development and integration with applications in need of translation services. This project seeks to make translation services easy to access for anyone by providing a FOSS alternative.

<div align="center">

</div>

<div align="center">
<img src="https://github.com/seanhlewis/seanhlewis/assets/96705270/6431249f-69f6-4de1-94d7-3ff50e500b74" width="800" />
</div>

## API Examples

### Simple

Request:

```javascript
const res = await fetch("https://translate.love/translate", {
  method: "POST",
  body: JSON.stringify({
    q: "Hello!",
    source: "en",
    target: "es"
  }),
  headers: { "Content-Type": "application/json" }
});

console.log(await res.json());
```

Response:

```javascript
{
    "translatedText": "¡Hola!"
}
```

### Auto Detect Language

Request:

```javascript
const res = await fetch("https://translate.love/translate", {
  method: "POST",
  body: JSON.stringify({
    q: "Ciao!",
    source: "auto",
    target: "en"
  }),
  headers: { "Content-Type": "application/json" }
});

console.log(await res.json());
```

Response:

```javascript
{
    "detectedLanguage": {
        "confidence": 83,
        "language": "it"
    },
    "translatedText": "Bye!"
}
```

### HTML (beta)

Request:

```javascript
const res = await fetch("https://translate.love/translate", {
  method: "POST",
  body: JSON.stringify({
    q: '<p class="green">Hello!</p>',
    source: "en",
    target: "es",
    format: "html"
  }),
  headers: { "Content-Type": "application/json" }
});

console.log(await res.json());
```

Response:

```javascript
{
    "translatedText": "<p class=\"green\">¡Hola!</p>"
}
```
## Supported Languages
English, Arabic, Azerbaijani, Catalan, Chinese, Czech, Danish, Dutch, Esperanto, Finnish, French, German, Greek, Hebrew, Hindi, Hungarian, Indonesian, Irish, Italian, Japanese, Korean, Persian, Polish, Portuguese, Russian, Slovak, Spanish, Swedish, Turkish, Ukranian

## Credit

This translation API was only made possible through the LibreTranslate project. Please support their efforts [here](https://github.com/LibreTranslate/LibreTranslate).
