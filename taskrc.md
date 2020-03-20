# Statement Journals - overview

- This content on both [Dropbox](https://www.dropbox.com/home/j-poli-sci) and [github](https://github.com/Stabledog/j-poli-sci)

## Workflow
- There's 2 essays per week, 10 weeks.  Each has readings and a statement that you're supposed to respond to from [this list](ref/poli_sci_statement_journals.md).
- The essays are written in markdown, in each week folder, named like 'sj3-response' *(Essays are sequentially numbered through the class)*
- The essay content is converted markdown-to-html with pandoc and then shared with Jacinta over Dropbox, like [sj1-response.html](https://www.dropbox.com/home/j-poli-sci/week_1?preview=sj1-response.html)

Finished content:
- [week_1..week_2]

Rough content:
- Use `make_rough_html()` to unify the unfinished sj*md files into an html doc, these are rough notes

```bash

function make_rough_html {
    cd $taskrc_dir
    pandoc -s -f markdown -t html $(cat rough-mdfiles) > rough.html || return
    echo "Updated: $(ls -l rough.html)"
}

function to_html {
    #Help provide a markdown and we'll write an html from it
    [[ -f $1 ]] || { echo "ERROR: No markdown file provided in \$1"; return; }
    pandoc -s -f markdown  -t html $1 > ${1/\.md/.html}
}
#source_taskrc ./week_1
```
