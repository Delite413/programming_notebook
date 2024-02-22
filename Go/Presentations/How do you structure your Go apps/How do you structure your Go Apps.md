---
Presentor: Kat Zien
Event: GopherCon 2018
---
# Good Structure Goals

* Consistent
* Easy to understand, navigate and reason about
* Easy to change, loosely-coupled
* Easy to test.
* "As simple as possible, but no simpler."
* Design reflects exactly how the software works.
* Structure reflects the design exactly.


# Structures

## Flat Structure

* data.go
* handlers.go
* main.go
* model.go
* storage.go
* storage_json.go
* storage_mem.go

## Layered Structure

* data.go
* handlers
	* beers.go
	* reviews.go
* main.go
* models
	* beer.go
	* review.go
	* storage.go
* storage
	* json.go
	* memory.go

## Group by Module

* beers
	* beer.go
	* handler.go
* main.go
* reviews
	* handler.go
	* review.go
* storage
	* data.go
	* json.go
	* memory.go
	* storage.go

## Group by Context

* adding
	* endpoint.go
	* service.go
* beers
	* beer.go
	* sample_beers.go
* listing
	* endpoint.go
	* service.go
* main.go
* reviewing
	* endpoint.go
	* service.go
* reviews
	* review.go
	* sample_reviews.go
* storage
	* json.go
	* memory.go
	* type.go

## Hexagonal Architecture

* cmd
	* beer-server
		* main.go
	* sample-data
		* main.go
* pkg
	* adding
		* beer.go
		* sample_beers.go
		* service.go
* http
	* reest
		* handler.go
* listing
	* beer.go
	* review.go
	* service.go
* reviewing
	* review.go
	* sample_reviews.go
	* service.go
* storage
	* json
		* beer.go
		* data
			* beers
			* reviews
		* repository.go
		* review.go
	* memory
		* beer.go
		* repository.go
		* review.go























































































