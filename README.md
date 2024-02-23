# CSS Notes

### Cascade rules
CSS combine stylesheets from the authors (coder) and browsers (user agent). Process of combining them is called - 
`Cascade`. </br>
When multiple selectors target the same elements using the same properties, the conflicts are resolved via the
`Cascade`. </br>
If styles lives in multiple resources, they are combine into one stack and then parsed. </br>
Order of priority:
1. Important user agent declaration
2. Important author declaration
3. Normal author declaration
4. Normal user agent declaration

- Origin & Importance
  - Origin - where are styles came from (style.css or browser)
  - Importance - `!importnat` key declaration. Could be used when author do not have full control over CSS (3rd part)
- Specificity - if styles declarations have a conflicts, specificity calculate the priority based on
  - count id's of selectors (1point)
  - count classes of selector (1 point)
  - count type and pseudo-elements (1 point)
  - modern IDE calculates all above for you
```css
#skills               100
#skills .resume-list  110
.skills               010
section.skills        011

 /*so we can sort it like */
#skills .resume-list  110
#skills               100
section.skills        011
.skills               010

/*so #skills .resume-list wins and it styles will apply*/
```
- Order of Appearance - if after all above styles still in conflict, the last style in the list wins.
```css
font-weith: bolder; 110
font-weith: bold; 110 // this will wins
```
