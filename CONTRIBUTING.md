# Sharing a vocabulary list

Hush's code is not public, so this repository takes one kind of contribution: vocabulary lists. If you teach, study or work in a subject with words of its own, you can share a list for it, and anyone can import it into Hush.

To report a bug or ask for a feature, [open an issue](https://github.com/IrtizaNasar/Hush/issues) on this repository.

## What a list does

A speech model writes what it thinks it heard. A subject's names and terms often come out wrong: "ML five JS" for ml5.js, "analog read" for analogRead. A list tells Hush how they're spelt. Before each stretch of speech, Hush gives the speech model up to 40 terms from the lists that are on, the ones that stretch seems to need, and the model leans towards their spellings.

## The format

One Markdown file per subject, like the three in [`vocabulary/`](vocabulary/):

```markdown
# Organic chemistry

> Terms for teaching organic chemistry: functional groups, reactions, techniques and people. To use them, open Settings › Vocabulary in Hush and import this file.
> One term per line, written as it should appear in a transcript.

## Functional groups
- alkene
- carboxylic acid
- benzene ring

## Techniques
- NMR spectroscopy
- thin-layer chromatography
- Grignard reaction
```

- **The first heading** is the list's name in Hush.
- **The quote** says what the list covers and how to import it. Hush skips it.
- **The `##` headings** group the terms. Hush skips them too.
- **Each term** is a bullet of its own, written exactly as it should appear in a transcript.

## Naming

- Name the file after the subject, in lower case with hyphens: `organic-chemistry.md`.
- One list per subject. A big subject gets more `##` headings, not more files.
- If there's already a list for your subject, add to it rather than starting another.

## Good terms

- **Words a speech model gets wrong.** Names of people, places and tools, acronyms, code such as `analogRead()` and `setup()`, words from other languages, and jargon that sounds like everyday words. Words it already spells right don't need to be there.
- **Written as they appear in the middle of a sentence.** Capitals only where they belong: `gradient descent`, but `PyTorch`, `Arduino Uno` and `mRNA`. Hush copies capitals into the transcript.
- **Spelt right.** Check each term against its own source: the project's site, the datasheet, the way a person writes their own name. Keep accents, as in Sierpiński and Hübner.
- **British spelling for everyday words**, as the other lists use (behaviour, colour, optimiser). Names, products and code keep their own.
- **Short.** Five words or fewer, and 48 characters at most. Hush leaves out anything longer.
- **Once each.** The same term in other capitals is kept once, as first written.
- **Up to 5,000 terms.** Long lists are fine: Hush picks the terms each stretch of speech seems to need.

Keep punctuation that belongs to a term, as in p5.js, Max/MSP and C++. Leave out what Hush reads as something else:

- Commas and semicolons separate terms, so a term can't contain one.
- A colon followed by a space, or a dash with spaces round it, starts a definition: `term: meaning` and `term - meaning` keep only the term.
- A line that ends with a full stop and has three words or more is read as a sentence and skipped.

## Check it in Hush

Import your file in **Settings › Vocabulary** › **Import…** and open the list. Hush shows every term it found. Check the count matches your bullets, and that each term reads exactly as you wrote it.

## Send it

1. Add your file to `vocabulary/`, and add its name to the list in `vocabulary/README.md`.
2. Open a pull request. Say what the subject is, who the list is for, and how you checked the terms.

No Git? On GitHub, open `vocabulary/`, choose **Add file › Create new file**, paste your list and name the file. GitHub makes a copy of the repository for you and offers to open the pull request.

Each list is read through before it's added, and small fixes may be suggested.
The lists are shared under [CC0](vocabulary/LICENSE): anyone can use, change and share them, with no need to give credit. By sending a list, you agree to share it the same way.
