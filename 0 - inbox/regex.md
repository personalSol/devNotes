---
status: newBorn
related-links: 
created: 2025-06-12T10:42
updated: 2025-06-12T10:42
---
---

## ✅ What is Regex?

**Regex** (short for **Regular Expression**) is a sequence of characters used to **define search patterns**.  
It is commonly used for:

- **Validation** (e.g., email, password, phone numbers)
- **Pattern Matching** (e.g., finding specific words in text)
- **Search & Replace** (e.g., replacing dates, formatting strings)

---

## ✅ Common Uses of Regex

- Validate input (emails, passwords, phone numbers)
- Extract specific patterns from text
- Replace or remove unwanted characters
- Text searching (logs, files, strings)

---

## ✅ Regex Vocabulary Cheat Sheet

|Symbol|Meaning|Example|
|---|---|---|
|`.`|Any single character|`a.c` matches `abc`, `axc`|
|`*`|0 or more of the previous character|`a*` matches `a`, `aa`, `aaa`|
|`+`|1 or more of the previous character|`a+` matches `a`, `aa`, `aaa`|
|`?`|0 or 1 of the previous character|`a?` matches `a` or nothing|
|`^`|Start of string|`^a` matches `apple` but not `banana`|
|`$`|End of string|`a$` matches `pizza` but not `apple`|
|`[]`|Character set (matches any one inside)|`[aeiou]` matches any vowel|
|`[^ ]`|Negated set (matches anything except inside)|`[^aeiou]` matches consonants|
|`{n,m}`|Between n and m repetitions|`a{2,4}` matches `aa`, `aaa`, `aaaa`|
|`\d`|Any digit (0-9)|`\d\d` matches `23`, `99`|
|`\w`|Any word character (a-z, A-Z, 0-9, _)|`\w` matches `a`, `Z`, `0`, `_`|
|`\s`|Any whitespace|`\s` matches space, tab, newline|
|`|`|OR operator|
|`()`|Grouping|`(abc)+` matches `abc`, `abcabc`|

---

## ✅ Example: Validate At Least 2 Special Characters

### Regex:

```regex
^(?:[^!@#$%^&*()_+\-=\[\]{};':"\\|,.<>\/?]*[!@#$%^&*()_+\-=\[\]{};':"\\|,.<>\/?]){2,}.*
```

### Breakdown:

|Part|Meaning|
|---|---|
|`^`|Start of the string|
|`(?:...)`|Non-capturing group|
|`[^!@#...]*`|Matches any number of characters **except** special characters|
|`[!@#... ]`|Matches **one special character**|
|`{2,}`|Requires the pattern to appear **at least 2 times**|
|`.*`|The rest of the string can be anything|

### Covered Special Characters:

```text
! @ # $ % ^ & * ( ) _ + - = [ ] { } ; ' : " \ | , . < > / ?
```

---

## ✅ Example Validations:

- ✅ `abc@#def` → Valid (contains `@` and `#`)
- ✅ `12!hello*` → Valid (contains `!` and `*`)
- ❌ `password@` → Invalid (only 1 special character)

---

