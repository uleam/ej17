- #+BEGIN_TIP
  Store the remarkable files for the course.
  #+END_TIP
- # All elements
  heading:: true
	- {{query (page-property source [[Elements]])}}
-
- # Closed
	- {{query (and (page-property source [[Elements]]) (not (page-property status closed)))}}
-
- # Category
	- ### Activity roadmap
	  collapsed:: true
		- {{query (and (page-property source [[Elements]]) (page-property category Activity_roadmap))}}
	- ### Instrument
	  collapsed:: true
		- {{query (and (page-property source [[Elements]]) (page-property category Instrument))}}
	- ### Session material
	  collapsed:: true
		- {{query (and (page-property source [[Elements]]) (page-property category Session_material))}}
-
-
-