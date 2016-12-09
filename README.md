# vue-search

> Components built with vue.js to provide an easier access to elasticsearch (search box, table for the hits, charts, ...)

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

# Examples:
``` html
<search host="localhost" port="9200" index="my_index" doc-type="my_doc_type" result-size="1000">
  <searchbox id="my_search_id"/>

  <search-table cols="name, age" search-id="my_search_id">
  </search-table>
  
  <search-chart search-id="my_search_id" type="donut" key="age" aggs="age">
  </search-chart>
</search>
```