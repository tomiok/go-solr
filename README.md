go-solr
=======

Json only

No schema checking

Please go to http://wiki.apache.org/solr/ for how to write solr query.

## Features

Search, Add, Update, Delete, Commit, Rollback, Optimize

Core admin, Schema REST API

## Install

go get github.com/tomiok/go-solr/solr

## Usage

    package main
    import (
    	"github.com/tomiok/go-solr/solr"
    	"fmt"
    )
  
    func main() {
      si, _ := solr.NewSolrInterface("http://localhost:8983/solr", "collection1")
      query := solr.NewQuery()
      query.Q("*:*")
      s := si.Search(query)
      r, _ := s.Result(nil)
      fmt.Println(r.Results.Docs)
    }
    
## Developers

	export MOCK_LOGGING=1

for the mock logging

	unset MOCK_LOGGING

to remove this environment variable
	
## License
MIT
