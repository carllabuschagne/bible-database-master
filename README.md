# Bible-Master

A JSON database of Catholic Church documents, a Catholic English Bible, and Bible reference data.

## Structure

```
catholic/     Catholic Church documents (Catechism, Canon Law, Missal, Rosary)
bibles/       English Bible (CPDV)
*.json        Bible reference datasets (books, apostles, parables, miracles, ...)
```

## Catholic documents (`catholic/`)

| File | Contents | Records |
|---|---|---|
| `The-catechism-of-the-catholic-church.json` | Catechism of the Catholic Church | 2,865 paragraphs |
| `the-code-of-canon-law.json` | Code of Canon Law (1983) | 1,751 canons |
| `the-general-instruction-of-the-roman-missal.json` | General Instruction of the Roman Missal | 399 paragraphs |
| `The-mysteries-of-the-most-holy-rosary.json` | Mysteries of the Rosary (Joyful, Luminous, Sorrowful, Glorious) | 20 mysteries |
| `The-prayers-of-the-holy-rosary.json` | Prayers of the Rosary | 8 prayers |

### Formats

- **Catechism, GIRM:** `[{ id, text }]`, where `id` is the paragraph number
- **Canon Law:** `[{ id, text }]` or `[{ id, sections: [{ id, text }] }]` for canons with numbered sections (§)
- **Mysteries:** `[{ set, sequence, title, description }]`
- **Prayers:** `[{ id, title, text }]`

## English Bible (`bibles/`)

| File | Translation | Books | Verses |
|---|---|---|---|
| `CPDV.json` | Catholic Public Domain Version | 78 | 37,255 |

The file contains the 73-book Catholic canon. It also lists the Vulgate appendix books
(Prayer of Manasses, I–II Esdras, Psalm 151, Laodiceans), but these have no text.

### Format

`{ books: [{ name, chapters: [{ chapter, name, verses: [{ verse, chapter, name, text }] }] }] }`

## Reference datasets

| File | Contents |
|---|---|
| `books.json` | All 66 Protestant-canon books: category, author, date written, summary |
| `bible-meta-data.json` | Book categories and testament groupings (KJV canon) |
| `apostles.json` | The apostles: death, and churches founded |
| `life-of-jesus.json` | Timeline of the life of Jesus (14 events) |
| `miracles-of-jesus.json` | 37 miracles of Jesus with Gospel references |
| `parables-of-jesus.json` | 30 parables with reference, theme, and summary |
| `prophecies.json` | Messianic prophecies, grouped into sections |
| `ten-commandments.json` | The Ten Commandments with explanations |

## Known gaps

- `the-code-of-canon-law.json` is missing canon 1697.
- The CPDV appendix books (Prayer of Manasses, I–II Esdras, Psalm 151, Laodiceans) are empty.

## Copyright

The CPDV is in the public domain. The Catechism, the Code of Canon Law and the GIRM
are copyrighted English translations (USCCB / Libreria Editrice Vaticana / Canon Law
Society of America / ICEL). Check their licence terms before publishing or
redistributing them.
