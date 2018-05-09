# Tables in Org Mode — quick tips

To add a 2x2 table, do `C-c |` and type "2x2" in prompt. This will create an empty table:

```org
|   |   |
|---+---|
|   |   |
```

Fill in this table a bit, remember that `TAB` moves to the next cell _and_ reformats the table along the way:

```org
| Item                    | Links somewhere? |
|-------------------------+------------------|
| Sign In                 | /login           |
| Register a free account | /signup          |
| Special offers          |                  |
| Cart                    |                  |
```

A few tips from this point:

- `C-c SPC` to blank current cell,
- `M-LEFT` to move current column one column left, `M-RIGHT` to move it right,
- `M-UP` to move current row up, `M-DOWN` to move it down,
- `M-S-RIGHT` to add a new column and move current column to the right; same for other arrows,

## Add columns and rows

Knowing this, we can add columns and rows quickly:

- `M-S-RIGHT M-RIGHT` adds a new column and puts it to the right of the current one.
- however, `M-S-DOWN M-DOWN` adds a row above and moves it below current row.

## Quickly add a timestamp

Not directly related to tables but still useful: `C-c . RET` inserts a timestamp.

Doing `M-S-RIGHT M-RIGHT` to add a column and `C-C . RET` to put timestamps gives this:

```org
| Item                    | Links somewhere? | Implemented     |
|-------------------------+------------------+------------------|
| Sign In                 | /login           | <2018-05-09 Wed> |
| Register a free account | /signup          | <2018-05-08 Tue> |
| Special offers          |                  |                  |
| Cart                    |                  |                  |
```

Now sort by time: put cursor anywhere in "Implemented" column and perform `C-c ^ t`:

```org
| Item                    | Links somewhere? | Implemented      |
|-------------------------+------------------+------------------|
| Special offers          |                  |                  |
| Cart                    |                  |                  |
| Register a free account | /signup          | <2018-05-08 Tue> |
| Sign In                 | /login           | <2018-05-09 Wed> |
```

Empty cells bubble up, giving a quick overview of what's yet to be implemented.

This is pretty much all the basics for tables. There is amazing [official tutorial](https://orgmode.org/worg/org-tutorials/tables.html) that gives a lot more to think about and learn, but the commands mentioned above are enough to cover 3/4 of all operations that are typically done using tables.
