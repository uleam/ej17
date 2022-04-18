- #+BEGIN_NOTE
  Track and add class materials by matter, week and type.
  #+END_NOTE
-
- # Line-up
-
- ## Per matter
	- ### Matter 1
	  collapsed:: true
		- {{query (and (page-property source [[Resources]]) (page-property subject [[Matter 1]]))}}
		  query-properties:: [:page :subject :type :submission :week :source]
	- ### Matter 2
	  collapsed:: true
		- {{query (and (page-property source [[Resources]]) (page-property subject [[Matter 2]] ))}}
-
- ## Overall
	- {{query (page-property source [[Resources]]))}}
	  query-properties:: [:page :subject :type :submission :week :source]
-
-