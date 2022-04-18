- ### Sections
  :logbook:
   CLOCK: [2022-02-03 Thu 23:22:48]--[2022-02-03 Thu 23:22:49] =>  00:00:01
   CLOCK: [2022-02-03 Thu 23:22:53]
  :END:
	- Workflow
		- [[Overview]]
		- [[Schedule]]
		- [[Stint development]]
	- Materials
		- [[Resources]]
		- [[Classtime]]
	- Apprenticeship program
		- [[Elements]]
		- [[Records]]
		- [[Documentation]]
	- [[Templates]]
		- ((8e893cb1-0409-4989-83b9-8a69115583fd))
		- ((6a9b0ae4-8c78-4b52-80a9-ea26f3662002))
		- ((53324c29-c09a-4f87-9916-b53ab38487a3))
		- ((65ff128e-e3fc-4174-9984-65623f4452d9))
		- ((3d7a74c5-4bff-423d-ac9f-d1bf6b2132f4))
		- ((504e8349-b466-4352-a5ff-f03ba531b21d))
-
- ## Extra
	- ### Tasks per matter
collapsed:: true
		- From all sources
			- ```
			  				  collapsed:: true
			  				  {{query (page-property subject [[Matter 1]] )}}
			  ```
				- {{query((page-property subject [[Matter 1]] ))}}
		- Only from one source: [[Schedule]]
			- ```
			  				  {{query (and (page-property source [[Schedule]] ) (page-property subject [[Matter 1]]) (not (page-property source [[Stint development]] )) ) }}
			  ```
				- {{query((and (page-property source [[Schedule]] ) (page-property subject [[Matter 1]]) (not (page-property source [[Stint development]] )) ) )}}
	- ### All matters
collapsed:: true
		- Pages using subject property
			- ```
			  				  {{query (page-property source)}}
			  ```
			- ```
			  				  {{query (or (page-property subject [[Matter 1]])  (page-property subject [[Matter 2]]) )}}
			  ```
		- Exclude one source: [[Stint development]]
			- ```
			  				  {{query (and (page-property source [[Schedule]] ) (not (page-property source [[Stint development]] )))}}
			  ```
				- {{query((and (page-property source [[Schedule]] ) (not (page-property source [[Stint development]] ))))}}
			-
		- Exclude one matter
			- ```
			  				  {{query (and (page-property subject [[Matter 1]]) (not (page-property subject [[Matter 2]])))}}
			  ```
				- {{query((and (page-property subject [[Matter 1]]) (not (page-property subject [[Matter 2]]))))}}
				-
		- Show just homework
			- ```
			  				  {{query (page-property type homework)}}
			  ```
				- {{query((page-property type homework))}}
	- ### Taskmap
collapsed:: true
		- Not started
			- ```
			  {{query (and (page-property subject [[Matter 1]]) (page-property status Not_started))}}
			  ```
		- In progress
			- ```
			  {{query (and (page-property subject [[Matter 1]]) (page-property status In_progress))}}
			  ```
		- Done
			- ```
			  {{query (and (page-property subject [[Matter 1]]) (page-property status Done))}}
			  ```
-