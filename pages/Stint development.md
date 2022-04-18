- #+BEGIN_NOTE
  This query below works as a database by storing major pages containing source property namely "Stint development".
  #+END_NOTE
-
- # Works
- {{query (and (page-property source [[Stint development]]) (not (page-property source [[Schedule]] )) ) }}
  query-properties:: [:page :subject :submission :source :file :task]
-