# Coding Standards

All GoSource developers will observe the following coding standards. Usage of automated checking tools like eslint or flake8, including plugins for your text editor, is highly encouraged.

## General

Please remember that it's important to increase code readability and avoid visual clutter from automated code checking tools because of just space in a wrong place. Following code standards helps another developers to read your code and saves their time.

## HTML

Please use coding standards defined for the framework you use. For example, for Bootstrap it means 2 spaces indentation and so on. General rules are:

* 2 spaces for intentation
* double quotes for attribute values (`<img src="..." />`)
* use multiple lines for long tags:
```
<button
   type="submit"
   class="btn btn-primary fullwidth-xls no-print"
   onClick="...."
   title="By pressing this button you accept the thing"
   disabled
   >
    Button text
</button>
```

instead of

```
<button type="submit" class="btn btn-primary fullwidth-xls no-print" onClick="...." disabled title="By pressing this button you accept the thing">Button text</button>
```

Of course there is no need to apply that for all the cases, only when you have very long unreadable lines.


## Python

See the coding standards page in the [pythonista](/pythonista/coding_standards.md) directory.

## Java

(todo)

## Javascript

Please tend to use AirBnb code standards if nothing else is specified.
