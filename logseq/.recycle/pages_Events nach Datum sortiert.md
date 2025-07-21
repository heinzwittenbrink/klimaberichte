- ```
  #+BEGIN_QUERY
  {:title "Events sorted by start date"
   :query [:find (pull ?b [*])
    :where
     [?b :block/properties ?props]
     [(get ?props :type) ?type]
     [(= ?type "event")]
    ]
  }
  #+END_QUERY
  ```