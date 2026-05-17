# File I/O Practice

## Create File

```bash
touch notes.txt
```

Created an empty file named `notes.txt`.

---

## Write First Line

```bash
echo "Linux is important for DevOps" > notes.txt
```

Added first line using `>` redirection.

---

## Append Second Line

```bash
echo "cat command is used to read files" >> notes.txt
```

Appended second line using `>>`.

---

## Append Third Line Using tee

```bash
echo "tail command reads last lines" | tee -a notes.txt
```

Used `tee` to display and append text at the same time.

---

# Read Full File

```bash
cat notes.txt
```

# Read First Two Lines

```bash
head -n 2 notes.txt
```

# Read Last Two Lines

```bash
tail -n 2 notes.txt
```

# Key Learnings

- Learned file creation using `touch`
- Practiced file writing using `>` and `>>`
- Used `cat`, `head`, and `tail` to read files
- Learned how `tee` works for writing and displaying output
