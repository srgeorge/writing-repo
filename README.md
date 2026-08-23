# Writing Repo

Basic git repository for writing projects, includes a very basic `docx` reference for guiding pandoc in converting your markdown to Word format.  If you want something different, write  a few sample pages in a word doc, format properly and apply the styles using the `Format > Style` in Word.  Save it to your reference file, eg. `mss-ref.docx`.  Then delete all the content inside the file; the defined styles will remain.

## Setup instructions

Download this repository.  Push to your own github or gitlab repo for your project, or just work privately on your own system if you prefer.

## Writing

Write in [Markdown](https://www.markdownguide.org/basic-syntax/)

Write all the chapters, sections, whatever, of your project in the source folder.  Best to number them sequentially if you plan on doing batch conversions.  eg.  `01-chapter.md, 02-chapter.md, etc.`


## Converting Markdown to Word

Use **pandoc** for conversion from Markdown to Word.  You can get the latest installer for your system here: [Installing Pandoc](https://pandoc.org/installing.html)

If you're using a Master Document in Word to manage your chapters or sections, you'll want to convert each Markdown file individually:

```bash
pandoc src/01-chapter.md -o build/01-chapter.docx --reference-doc mss-ref.docx 
```

If you want to convert all markdown files into one large manuscript, you can use the following command:

```bash
pandoc src/*.md  -o build/manuscript.docx --reference-doc mss-ref.docx 
```

## Be Careful

This repo ignores the following types of files; they will not be saved to your repository:

```
*.pdf
*.odt
*.doc
*.docx
*.zip
!mss-ref.docx
```

Note: the last line means it will NOT ignore a the `mss-ref.docx`, so any changes you make to that file will be preserved in the repo.

---
@updated 2026-08-23
  
  


