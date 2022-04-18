- Status
	- Not started
	  collapsed:: true
		- {{query (and (page-property subject [[Matter 1]]) (page-property status Not_started))}}
	- In progress
	  collapsed:: true
		- {{query (and (page-property subject [[Matter 1]]) (page-property status In_progress))}}
	- Completed
	  collapsed:: true
		- {{query (and (page-property subject [[Matter 1]]) (page-property status Done))}}
-
- # Roadmap
- {{query (page-property source [[Schedule]]) (page-property status)}}
  query-properties:: [:page :subject :type :status :submission :week :source :file]
-
- ## Subtasks
	- ### Current
	  collapsed:: true
		- query-table:: true
		  #+BEGIN_QUERY
		  {
		    :query [:find (pull ?h [*])
		            :in $ ?start ?next
		            :where
		            	[?h :block/marker ?marker]
		            	[?h :block/ref-pages ?p]
		            [?p :page/journal? true]
		            [?p :page/journal-day ?d]
		            [(> ?d ?start)]
		            [(< ?d ?next)]
		            [(contains? #{"NOW" "LATER" "DOING" "TODO"} ?marker)]]
		    :inputs [:today :31d-after]
		    :collapsed? false}
		  #+END_QUERY
	- ### Past
	  collapsed:: true
		- query-table:: true
		  #+BEGIN_QUERY
		  {
		  :query [:find (pull ?h [*])
		  :in $ ?start ?today
		  :where
		  [?h :block/marker ?marker]
		  [?h :block/ref-pages ?p]
		  [?p :page/journal? true]
		  [?p :page/journal-day ?d]
		  [(>= ?d ?start)]
		  [(<= ?d ?today)]
		  [(contains? #{"NOW" "LATER" "TODO" "DOING"} ?marker)]]
		  :inputs [:56d :today]
		  :collapsed? false}
		  #+END_QUERY
	- ### Arranged
	  collapsed:: true
		- query-table:: true
		  #+BEGIN_QUERY
		  {
		    :query [:find (pull ?block [*])
		            :in $ ?start ?next
		            :where
		            (or
		              [?block :block/scheduled ?d]
		              [?block :block/deadline ?d])
		            [(> ?d ?start)]
		            [(< ?d ?next)]]
		    :inputs [:today :31d-after]
		    :collapsed? false}
		  #+END_QUERY
	- ### Now - Later
	  collapsed:: true
		- query-table:: false
		  #+BEGIN_QUERY
		  {
		   :query [:find (pull ?b [*])
		          :where
		          [?b :block/marker ?marker]
		          (not [?b :block/scheduled ?d])
		          (not [?b :block/deadline ?d])
		          [(contains? #{"LATER" "NOW"}  ?marker)]]
		  }
		  #+END_QUERY
	- ### Closed
	  collapsed:: true
		- query-table:: false
		  #+BEGIN_QUERY
		  {
		  :query [:find (pull ?b [*])
		          :where
		          [?b :block/marker ?marker]
		          [(contains? #{"DONE"} ?marker)]
		          (not [?b :block/ref-pages ?p]
		               [?p :block/journal? true]) ]
		  :collapsed? false}]}
		  #+END_QUERY
-