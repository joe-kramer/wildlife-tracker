## Wildlife Tracker

An app for the forest service to track animals for an environmental impact study.

### Description

The Forest Service is considering a proposal from a timber company to clearcut a nearby forest of Douglas Fir. Before this proposal may be approved, they must complete an environmental impact study. This application was developed to allow Rangers to track wildlife sightings in the area.

### Setup

To create the necessary databases, launch postgres, then psql, and run the following commands:

* `CREATE DATABASE wildlife_tracker;`
* `\c wildlife_tracker;`
* `CREATE TABLE animals (id serial PRIMARY KEY, name varchar);`
* `CREATE TABLE endangered_animals (id serial PRIMARY KEY, name varchar, health varchar, age varchar);`
* `CREATE TABLE sightings (id serial PRIMARY KEY, animal_id int, location varchar, ranger_name varchar, timesighted timestamp);`
* `ALTER SEQUENCE endangered_animals_id_seq RESTART 1000;`
* `CREATE DATABASE wildlife_tracker_test WITH TEMPLATE wildlife_tracker;`

### Refactor

* _Make endangered animals class inherit from our Animal class_
* _Add timestamp to sightings_
* _Add tests for our timestamps in our AnimalTest and SightingTest_
* _Add constants to Animal class and set them as integer values for sorting later_
* _Add psql command to start endangered_animals_id at 1000_

### License

Copyright (c) 2017 **_MIT License_**
