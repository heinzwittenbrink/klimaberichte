template:: inline_literature_note
({author} {year})

- template:: citation _page
  alias:: {author lastname} ({year}) {title}
  tags:: [[publication]], [[Logseq citation manager]], 
  type:: {type};
  status:: 
  icon:: 📚
  
  - *{title}*. {publisher}.
  	- {author}, {year}.
  - Abstract:
  	- {abstract}
  - Notes
  	- {notes+}
  ```