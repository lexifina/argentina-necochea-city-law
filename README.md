# Necochea: municipal law history in git

The municipal law of the Partido de Necochea (Province of Buenos Aires), Argentina, as a git history: one file per article, one commit per ordinance on the day it took effect. `git log` lists the changes; checking out a date gives the text the record holds for that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `ar-b-necochea/`. The province's law is in [lexifina/argentina-buenos-aires-law](https://github.com/lexifina/argentina-buenos-aires-law) and Argentina's national law in [lexifina/argentina-law](https://github.com/lexifina/argentina-law).

The text is in Spanish, exactly as the source prints it.

## What this repository holds

2 ordinances so far, in force from 16 February 2025 to 14 June 2026, each as published in the Boletín Oficial Municipal de Necochea, added in parts.

| Folder | Ordinance | History |
| --- | --- | --- |
| `ordenanza-11687-2025/` | Ordenanza 11687/2025: La determinación, fiscalización, recaudación, calificación de contribuyentes, percepción de todos los tributos, y la aplicación de sancion… | in force 16 February 2025 |
| `ordenanza-12151-2026/` | Ordenanza 12151/2026: Autorícese al Departamento Ejecutivo a realizar Llamado a ---------------------- Licitación Pública para otorgar en Concesión el Servicio … | in force 14 June 2026 |

## Source

Sistema de Boletines Oficiales Municipales (SIBOM), Subsecretaría Legal y Técnica, Secretaría General, Provincia de Buenos Aires: Boletín Oficial Municipal de Necochea, <https://sibom.slyt.gba.gob.ar/cities/89>. SIBOM is the platform on which each municipality of the Province of Buenos Aires makes its Boletín Oficial Municipal (Ley 14.491). For each bulletin it lists the ordinances it published; each ordinance has its own page with the text as published (HTML). The site states no terms restricting reuse.

## Dates

- Each commit is dated at **noon, America/Argentina/Buenos_Aires, on the day the ordinance took effect**: the day its own vigencia clause names, or otherwise the ninth day after its publication in the Boletín Oficial Municipal de Necochea (Código Civil y Comercial de la Nación, arts. 5 and 6).
- Each ordinance is its text as published. Later ordinances that amend it are separate folders; their changes are not merged into the earlier text.
- Versions that take effect after the retrieval day are on the `futuro` branch, never merged into `main`.

## Files

`<ordinance>/art-005.md` is Artículo 5; `encabezado.md` holds the number, the place and date, the expediente line and anything printed before Artículo 1. Signatures and annexes stay in the file of the article they follow. One paragraph per line.

## How it is checked

- Every version of every ordinance is read back from git on the day it took effect and on the day before (`tools/check_repo.py`); both must match `corpus.json`.
- The letters and digits of every version equal those of the source page it was read from (read again with an independent HTML reader), so no word is lost or added.
- Health checks: no merge commits, commit dates never go backwards, nothing dated in the future, and every commit's trailers parse.

## Limits

This is not an official publication. The binding text is the one published in the Boletín Oficial Municipal de Necochea. Only the ordinances listed above are included, and amendments are not consolidated into the texts they amend.
