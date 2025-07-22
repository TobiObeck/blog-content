# Hallo Welt

Willkommen zu meinem ersten Blogeintrag! Wie in der Welt der Programmierung und der Erstellung digitaler Inhalte üblich, beginne ich mit einem obligatorischen "Hello, World!"-Artikel. Aber dies ist nicht wirklich eine Einführung. Vielmehr dient dieser Artikel dazu, Formatierung, Typografie und Funktionen wie Codehervorhebung oder Einbettung zu demonstrieren, hauptsächlich zu meiner eigenen Bequemlichkeit. Schaue dir also lieber einen anderen Artikel auf dem [Blog](/blog) an.

Vielleicht fällt dir auch die Funktion der geteilten Ansicht auf. Sie zeigt den Inhalt nebeneinander in verschiedenen Sprachen an, wobei jeder Absatz vertikal mit der Übersetzung beginnt. Dies ist ein Experiment, mit dem untersucht wird, ob dieses Layout zum Erlernen einer Sprache verwendet werden kann. Es wurde mit dem CSS-Untergitter und der Inhaltsfunktion erstellt.

Im weiteren Verlauf dieses Beitrags werden verschiedene Elemente und Formatierungen vorgestellt. Dies ist ein lebendiger Beitrag, der laufend aktualisiert wird.

## Formatierung Showcase

### Links & Listen

- [extern](https://google.com)
- [intern](/)
- [linking to same page headings](#gfm)

1. Erste
2. Zweite

### Code-Blöcke mit Syntax-Hervorhebung

Hier ist ein "Inline"-Stück Code und ein Code-Block:

```js
let processor = unified()
    .use(remarkParse)      // in einen Markdown-Syntaxbaum parsen
    .use(remarkRehype)     // in einen HTML-Syntaxbaum umwandeln
    .use(highlight)        // fügt Klassen für die Syntaxhervorhebung von Codeblöcken hinzu
    .use(rehypeStringify)  // wandelt den HTML-Syntaxbaum in HTML um

// Die process-Funktion gibt den erzeugten HTML-String zurück.
function processFile(filename) {
    // Liest die Datei mit vfile ein; man könnte auch fs verwenden, wenn man möchte.
    return processor.processSync(vfile.readSync(filename));
}
```

```diff
/// file: svelte.config.js
import adapter from '@sveltejs/adapter-node';

export default {
	kit: {
-		adapter: adapter()
+		adapter: adapter({ out: 'mein-ausgabe-verzeichnis' })
	}
};
```

Erheiternde Randbemerkung, am 01.01.1970 wurde die Zeit erfunden:

[https://de.wikipedia.org/wiki/Unixzeit](https://de.wikipedia.org/wiki/Unixzeit)

![Wunderschöne Flagge](./imgs/beautiful_flag.png "Dies ist der Alternativtext für eine deutsche Flagge")

## GFM

### Autolink literals

www.example.com, https://example.com, and contact@example.com.

## Fußnote

Eine Notiz[^1]

[^1]: Große Notiz.

## Durchgestrichen

~eins~ oder ~~zwei~~ Tilden.

## Eine Tabelle mit verschiedenen Textausrichtungen

| Normal | Links  | Rechts | Zentriert |
| - | :- | -: | :-: |
| 1 | 2 | 3 | 4 |

## Aufgabenliste

* [ ] aufgabe
* [x] erledigt

## Ein größere Tabelle mit Harry-Potter-Figuren

Figuren mit einem anderen Namen im Englischen sind **fett** markiert.

| Gryffindor             | Hufflepuff            | Ravenclaw            | Slytherin            | **Lehrer**                | Muggel               |
|------------------------|-----------------------|----------------------|----------------------|-----------------------|----------------------|
| Harry Potter           | Cedric Diggory        | Luna Lovegood        | Draco Malfoy         | Albus Dumbledore      | Vernon Dursley       |
| **Hermine** Granger        | Nymphadora Tonks      | Cho Chang            | Severus Snape        | Minerva McGonagall    | Petunia Dursley      |
| Ron Weasley            | Pomona Sprout         | Filius Flitwick      | Pansy Parkinson      | Severus Snape         | Dudley Dursley       |
| Neville Longbottom     | Newt Scamander        | Gilderoy Lockhart    | Blaise Zabini        | Rubeus Hagrid         | Marge Dursley        |
| Ginny Weasley          | Ernie Macmillan       | Sybill Trelawney     | Horace Slughorn      | Dolores Umbridge      | **Herr** Granger         |
| Sirius Black           | Hannah Abbott         | Marietta Edgecombe   | Regulus Black        | Remus Lupin           | **Frau** Granger         |
| James Potter           | Justin Finch-Fletchley| Michael Corner       | Tom Riddle           | Gilderoy Lockhart     | Mrs. Figg            |
| Lily Potter            |                       |                      | Bellatrix Lestrange  | Horace Slughorn       | Kathrin Fricke                     |
