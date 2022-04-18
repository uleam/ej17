- #+BEGIN_TIP
  Manage notes and work in class in one single place.
  #+END_TIP
-
- # Notes
	- {{query (and (page-property source [[Classtime]]) (page-property type classnote))}}
-
-
- # In-class work
	- {{query (and (page-property source [[Classtime]]) (page-property type classwork))}}