# `tokenize`

Returns tokenized text segments for input text, including readings.

## Request Options

- Request method: `POST`

- Body:

    - `text` (`string`): The text to tokenize and parse.

    - `scanLength` (`number`): Maximum length to scan for each segment. Lower values provide faster processing while higher values can capture longer compound words.

## Request Example

```json
{
    "text": "自民党の総裁選挙",
    "scanLength": 10
}
```

## Response Example (200)

The response contains an array with parsing results from Yomitan's internal `parseText` method. Each element in the content array represents a parsed segment with its reading(s) and text.

```json
[
    {
        "id": "scan",
        "source": "scanning-parser",
        "dictionary": null,
        "content": [
            [
                {
                    "text": "自民党",
                    "reading": "じみんとう"
                }
            ],
            [
                {
                    "text": "の",
                    "reading": ""
                }
            ],
            [
                {
                    "text": "総裁選",
                    "reading": "そうさいせん"
                }
            ],
            [
                {
                    "text": "挙",
                    "reading": "きょ"
                }
            ]
        ]
    }
]
```
