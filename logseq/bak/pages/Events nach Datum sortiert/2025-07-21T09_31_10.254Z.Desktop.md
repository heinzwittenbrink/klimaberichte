- #+BEGIN_QUERY
  {:title "Events sorted by start date"
   :query [:find ?name ?date-range
    :where
    [?b :block/properties ?props]
    [?b :block/name ?name]
    [(get ?props :type) ?type]
    [(= ?type "event")]
    [(get ?props :date-range) ?date-range]]
   :result-transform (fn [result]
    (sort-by (fn [[_name date-range]]
      (let [date-str (second (re-find #"\[(\d{4}-\d{2}-\d{2})" date-range))]
        date-str))
      (comp - compare)
      result))
  }
  #+END_QUERY