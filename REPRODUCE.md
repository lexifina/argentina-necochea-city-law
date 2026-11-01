# How this repository was made (Necochea)

This file is written by the build on 2026-11-01, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Sistema de Boletines Oficiales Municipales (SIBOM), Subsecretaría Legal y Técnica, Secretaría General, Provincia de Buenos Aires: Boletín Oficial Municipal de Necochea | <https://sibom.slyt.gba.gob.ar/cities/89> | 2026-11-01 | Official municipal ordinances, published in the Boletín Oficial Municipal. Argentina's copyright law (Ley 11.723) has no express exclusion for them; ordinances are public acts of government, binding on everyone once officially published. The source states no restriction on reuse. Reproduced with attribution, following the official text. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `ordenanza-11687-2025` | Ordenanza 11687/2025: La determinación, fiscalización, recaudación, calificación de contribuyentes, percepción de todos los tributos, y la aplicación de sanciones por el incumplimiento de obligaciones tributarias formales o materiales que est | 1 | 2025-02-16 to 2025-02-16 |
| `ordenanza-12151-2026` | Ordenanza 12151/2026: Autorícese al Departamento Ejecutivo a realizar Llamado a ---------------------- Licitación Pública para otorgar en Concesión el Servicio de Autotransporte Urbano de Pasajeros de las ciudades de Necochea y Quequén del Pa | 1 | 2026-06-14 to 2026-06-14 |

The build made 2 commits:

| Commits | Kind |
| ---: | --- |
| 2 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-11-01.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 2 laws in the record.
- 4 tags.

## Dates

Each commit is dated at noon (America/Argentina/Buenos_Aires) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: An ordinance takes effect on the day its own vigencia clause names; otherwise, as for any general norm, under Código Civil y Comercial de la Nación, art. 5 ("Las leyes rigen después del octavo día de su publicación oficial, o desde el día que ellas determinen"), counted under art. 6 (the day of publication excluded): the ninth day after its publication in the Boletín Oficial Municipal. The provincial Ley Orgánica de las Municipalidades (Decreto-Ley 6769/58, art. 108 inc. 2 and 18 as given by Ley 14.491) requires publication in the Boletín Oficial Municipal but sets no day of its own. https://normas.gba.gob.ar/ar-b/ley/2013/14491/11345

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `3b33b71d1965162e32edb0adedacc936522086c42144ac77d7e8594a9d409c16` (385020 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `a4faa25af85facb64b956b372f6b528aafdd7ec1`, `check.py` `3d00541d258745461ab52b1b0cb4e1716a27a95d`, `on.py` `644a6c0857fbcc72562032b58d57aa113fee0641`.
- Python 3.12.10; git version 2.46.0.windows.1.

## Checks

2 versions of 2 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Source: the Boletín Oficial Municipal de Necochea on SIBOM (https://sibom.slyt.gba.gob.ar/cities/89), the Province of Buenos Aires' platform for municipal bulletins (Ley 14.491). Each ordinance is its text as published in the bulletin, shown as enacted and dated the day it took effect. Later amendments by other ordinances are not applied to it; an amending ordinance appears as its own folder when it is included.
- In-force day: the ordinance's own vigencia clause when its last articles state one (from publication, the day after, or a named date). Otherwise our choice is the ninth day after its publication in the Boletín Oficial Municipal, applying Código Civil y Comercial, arts. 5 and 6, to ordinances as general norms: the Ley Orgánica de las Municipalidades requires publication but sets no day. The publication date is the one SIBOM prints for the bulletin.
- The Province of Buenos Aires gives its municipalities no carta orgánica: their organic law is the provincial Ley Orgánica de las Municipalidades (Decreto-Ley 6769/58), which is provincial law and not included here. So this repository starts with ordinances.
- Ordinances are taken from SIBOM's ordinance search for the partido, read from its last result page back (the search lists them only roughly in date order) until about 200 are found, the newest it holds. They are sorted by the day they took effect and added oldest first in parts of about 50, so each part extends the history forward. An ordinance whose page carries only an extract, no article, or its text only as a PDF annex is left out; the README lists every ordinance left out and why. An ordinance published twice is taken from its first publication.
- Units: the heading (encabezado: number, place and date, the expediente line and anything before Artículo 1) and one file per article, holding the article and everything printed after it up to the next article (signatures, annexes). Nothing is dropped. One paragraph per line, spacing normalised.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- A model (Claude) wrote the fetch and parse code and chose which norms to include; it wrote no law text. Every word of law comes from the provincial source's own texts.
