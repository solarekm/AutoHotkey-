# AutoHotkey Text Expander

A straightforward AutoHotkey v2 script that allows you to define custom hotstrings (text shortcuts) which automatically expand into full phrases, addresses, code snippets, or other blocks of text.

## Features

- **Hotstrings**: type a shortcut (e.g., `addr`) followed by a trigger key (`Space`, `Enter`, `Tab`, etc.) and it expands to the defined text.
- **Advanced options**:
  - `*` – match even inside other words (e.g., `:*:btw::by the way`).
  - `?` – expand without requiring an ending character.
  - `C` – case-sensitive hotstrings.
- **Dynamic content**: insert current date, time, or other AHK variables.
- **Emoji and symbols**: quickly insert common emoticons or unicode characters.

## Example Hotstrings

```ahk
#Requires AutoHotkey v2.0

; ===== Basic Expansions =====
::addr::123 Main St.`nAnytown, USA
::sig::Best regards,`nJohn Doe

; ===== Advanced Options =====
:*:btw::by the way               ; expand even inside other words
:?::id::system identifier        ; expand without delimiter
:?:C:Test::TestExact             ; case-sensitive, no delimiter required

; ===== Date and Time =====
::date::
{
    date := FormatTime(A_Now, "yyyy/MM/dd")
    SendText(date)
}
::time::
{
    time :=FormatTime(A_Now, "HH:mm")
    SendText(time)
}

; ===== Emoticons and Emoji =====
::shrug::¯\_(ツ)_/¯
::smile::😊

; ===== Contact Information =====
::tel::+1 (555) 123-4567
::email::your.email@example.com

; ===== Bracketed Shortcuts =====
::[br]::
{
    SendText("Best regards,`n")
    SendText("John Doe`n")
    SendText("123 Main St.`n")
    SentText("Anytown, USA")
}
```

## Installation and Usage

1. Install **AutoHotkey v2** from https://www.autohotkey.com/.
2. Create a folder named `TextExpander` in your repository or scripts directory.
3. Save this script as `TextExpander.ahk` within that folder.
4. Double-click `TextExpander.ahk` to run the script.

## Adding Your Own Hotstrings

Use the syntax:
```
:Options:Shortcut::ExpansionText
```
- **Options**: zero or more of `*`, `?`, `C`.
- **Shortcut**: the text you type to trigger the expansion.
- **ExpansionText**: the text to be inserted.

**Example**: `:*:omw::On my way…`

## License

This script is released under the MIT License. Feel free to modify and redistribute.

