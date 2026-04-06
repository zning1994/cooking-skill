# cooking.skill

> Wenn du nicht weißt, was du kochen sollst, sag einfach ehrlich, worauf du Lust hast und was im Kühlschrank liegt.

`cooking.skill` ist ein Koch-Skill, der nur die nötigsten Fragen stellt und dann ein Rezept liefert, das man wirklich kochen kann.

Standardfokus:

- chinesische Hausmannskost
- praktikable Techniken für normale Küchen
- lebendige, aber normale Sprache

## Was es kann

- Gerichte empfehlen
- mit vorhandenen Zutaten arbeiten
- konkrete Fragen zu Gerichten oder Techniken direkt beantworten
- Ersatzoptionen, Fehlstellen und Rettungen mitgeben

## Standardablauf

Die Skill unterscheidet automatisch zwischen:

- `worauf habe ich Lust`
- `was habe ich zu Hause`
- `wie mache oder rette ich dieses Gericht`

Wenn nötig, fragt sie höchstens zwei Dinge:

1. `für wie viele Personen`
2. `ob es Einschränkungen, fehlende Zutaten oder Technikgrenzen gibt`

## Standardausgabe

- was du kochen solltest
- warum das passt
- was du brauchst
- wie du es machst
- die wichtigsten Knackpunkte
- wahrscheinliche Fehler
- Ersatz- oder Rettungsoptionen

## Installation

```bash
mkdir -p .claude/skills
git clone https://github.com/zning1994/cooking-skill .claude/skills/cooking-skill
```

Global:

```bash
git clone https://github.com/zning1994/cooking-skill ~/.claude/skills/cooking-skill
```

