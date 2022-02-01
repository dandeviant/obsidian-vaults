Vim Cheat Sheet

---
**Modes in Vim and how to use it**

| Keys | Mode |
|--- | --- |
|Esc	| Normal Mode |
|i       |Insert Mode |
| V      | Visual Mode|
| \[Shift][;:] | Command Mode |

--- 

**Commands**

| Commands | Description |
| --- | --- |
| :q! |  Quit without saving |
| :w	  | Save changes |
| :wq / :x! | Save and quit |
| :2  | move to line 2 or any number |
| :$	 | move to last line |
 | \[Shift]+[6/^] | move to beginning of line |

---

**Normal Mode**

|Keys | Description |
| --- | --- |
| 2x[D] | Delete the whole highlighted line
| 2x[U] | Undo
| Hold [V] + [<]/[>] | Select and deselect text
| [Y] | yank mode / copy highlighted text
| [P] | paste after yank
| [O] | Enter new line (enter Insert Mode)
| :/\<KEYWORD> | search keyword in file |
| [N] | next search (NOT IN INSERT MODE) |

---

**Split Screen**

|Keys | Description |
| --- | --- |
| :split FILE_NAME  | split screen horizontally
| :vsplit FILE_NAME | split screen vertically
| [Ctrl]+[W] | switch window focus |
