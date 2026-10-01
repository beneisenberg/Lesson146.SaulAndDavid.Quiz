# שָׁאוּל בִּקֵּשׁ אֶת־דָּוִד לְהָמִית אֹתוֹ

Two interactive Biblical Hebrew comprehension games on 1 Samuel 19 and 24, Saul's pursuit of David and David sparing Saul in the cave at Ein Gedi: a fourteen-question quiz and a drag-and-drop cloze passage, both centered on the lesson's grammatical focus, the **infinitive construct**. Entirely in Hebrew with full niqqud, built for communicative / comprehensible-input classrooms.

Companion to Aleph with Beth [Lesson 146](https://www.youtube.com/watch?v=u_YBHgipd9k) (שָׁאוּל בִּקֵּשׁ אֶת־דָּוִד לְהָמִית אֹתוֹ).

## What it does

The start screen offers both games — **שְׁאֵלוֹת** and **מִלִּים** — and each links to the other when finished.

### שְׁאֵלוֹת — the quiz

Across the top of the screen hangs the hem of Saul's robe, its corner cut away — כְּנַף־הַמְּעִיל. Each correct answer turns one of its tassels blue. The hem is the score.

After every answer — right or wrong — the corresponding line of the biblical text appears, with Masoretic cantillation intact. The reward for answering is more Hebrew input, not a score animation. Questions missed along the way are collected into a review list at the end, so students can take them back to the video.

The infinitive construct runs through the questions as well as the answers. Several set it against a finite form of the same verb (לְהָמִית אֶת־דָּוִד / הֵמִית אֶת־דָּוִד, לְבַקֵּשׁ / בִּקֵּשׁ) or against the wrong pronominal suffix (לַהֲמִיתְךָ / לַהֲמִיתֵנִי / לַהֲמִיתוֹ). One, ״לַהֲמִיתְךָ״ — מַה־זֶּה?, drills the equivalence between the suffixed infinitive and לְהָמִית אֹתְךָ. The rest are content questions with infinitives built into them, such as אִישׁ אָמַר לַהֲרֹג אֶת־שָׁאוּל. מָה אָמַר דָּוִד?

The correct answer is never the first option — it is placed second, third or fourth at random — so students have to read past the first choice every time.

### מִלִּים — the cloze passage

The story appears in full, with words missing. A bank of word tiles sits beside the text, or pinned to the bottom of the screen on a phone. Students drag each word into its place, or tap a word and then tap its place, which is the dependable method on touchscreens. Tapping a filled blank returns the word to the bank.

Fifteen words are missing; four of them are infinitives (לְהָמִית, לְבַקֵּשׁ, לָקוּם, לַהֲרָגֲךָ). Eight of the tiles belong nowhere. Most are finite forms of the same verbs, or the wrong number or suffix — הֵמִית, בִּקֵּשׁ, קָמוּ, לְהָרְגֵנִי, יָדְעוּ, אָבִיךָ, מְעִילִי, and אֲנִי for אַתָּה in צַדִּיק אַתָּה מִמֶּנִּי. Students can't eliminate them on meaning alone; they have to read the form.

Nothing is graded until the student presses **הַאֱמֶת?** — the interrogative הַ before a guttural, not the article — so the passage can't be solved by trial and error. Correct words are marked, wrong ones can be tapped back into the bank and tried again. When every word is in its place, every tassel on the hem turns blue.

Only words that carry no taamim in the lesson text are blanked, so no tile ever has an accent stranded on it.

There is no English anywhere in the interface.

## Reading controls

Three small buttons beside the lesson label: **א−** and **א+** step the text size down and up (six sizes), and the moon / sun switches between the light and dark palettes. The page opens in light mode. Both choices are remembered in that browser — and because GitHub Pages serves every repository under one address, a student's choice carries over to every game on the site.

The page declares `color-scheme`, so browsers with their own forced dark modes (Samsung Internet, Chrome's auto-dark, Opera) leave it alone and the switch decides. Darkening extensions such as Dark Reader can still override it.

## Running it

One self-contained HTML file. No build step, no dependencies, no server-side anything. Open `index.html` in a browser and it works, including offline.

Nothing is transmitted: no accounts, no analytics, no cookies, no saved progress. The only thing kept is the reader's text size and light/dark choice, in the browser's own storage. Students need only the link.

## Typography

Hebrew is set in **SBL Hebrew** (Tiro Typeworks, v1.56a), embedded in the file so every student sees the same rendering regardless of what is installed on their machine. The `@font-face` rule lists `local("SBL Hebrew")` first, so anyone who already has it installed loads their own copy and skips the \~315 KB download.

Type is set in the regular weight throughout. SBL Hebrew ships no bold, and synthetic bold smears badly over niqqud and taamim, so hierarchy runs on size and color instead. Leading is opened up well beyond a Latin-typeface default to keep cantillation above and below the baseline from colliding between lines.

## Adapting it

All fourteen quiz questions live in the `Q` array near the bottom of `index.html`. Each entry has the question (`q`), four options (`o`), and the verse shown as feedback (`v`). **The correct answer is always first in `o`**. At runtime it is placed second, third or fourth, and the other options are shuffled around it. The row of tassels sizes itself to the number of questions.

The cloze passage is the `CLOZE` array, one string per line of the story, with each blank written in braces: `וְאֶת־{נָשָׁיו}`. A word after maqaf stays joined to its blank when the line wraps, and so does punctuation directly after it. The fake tiles are the `FAKES` array. Blanks are graded by exact text, so a tile has to match its blank in every point of niqqud.

To build games for a different passage, replace `Q`, `CLOZE`, `FAKES` and the title. Nothing else is passage-specific.

## License

The game — text, questions, code, design — is released into the **public domain (CC0)** by Ben Eisenberg / Lingua Deo Gloria, for the free use of the global church. Copy it, translate it, adapt it, teach with it, sell it, no attribution required.

**The embedded font is not covered by that dedication.** SBL Hebrew is © John Hudson, Tiro Typeworks, 2003 \& 2007; SBL Hebrew is a trademark of the Society of Biblical Literature. It is redistributed here unmodified, with its embedding bit unaltered, under clauses 3 and 5 of the [SBL Font End User License Agreement](https://www.sbl-site.org/wp-content/uploads/2024/05/SBL_Font_End_User_License_Agreement.pdf), which permit free redistribution of the unmodified software and embedding in non-commercial electronic documents including web pages. The full license text travels inside `index.html`.

That license covers non-commercial use only. If you intend to use this commercially, contact the Society of Biblical Literature for a font license, or swap the `@font-face` rule for an open-licensed Hebrew face with cantillation support — Taamey Frank CLM, Taamey David, Keter YG, Ezra SIL and Cardo are all good candidates.

