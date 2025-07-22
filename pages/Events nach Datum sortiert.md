- #+BEGIN_QUERY
  {:title "Events sorted by start date"
   :query [:find ?page ?date-range
    :where
     [?page :block/properties ?props]
     [(get ?props :type) ?type]
     [(= ?type "event")]
     [(get ?props :date-range) ?date-range]
    ]
   :result-transform (fn [result]
                       (sort-by (fn [[_page date-range]]
                                  (subs date-range 1 11))
                                result))
  }
  #+END_QUERY