# Influx CLI Cheat Sheet

## Connect

Connect the client to the data base. `-precision` specifies the time stamp format of DB results.

    influx -precision rfc3339

Connect to a data base running on a specific host (default values are host `localhost` and port `8086`)

    influx -host <host> -port <port> -precision <precision>

## Data Base

Show available data bases

    show databases

Create a data base

    create database <name>

Set the data base for further requests

    use <name>

Drop data base

    drop database <name>

## Measurements

Show available data bases

    show measurements

Drop (delete) measurement from data base

    drop measurement <name>

## Values

Insert an entry to the data base. The number of tags and files may vary.

    insert <name>,<tag1>=<value>,<tag2>=<value> <field1>=<value>,<field2>=<value>

Query all values for a measurement

    select * from <name>

Query and filter values for a measurement. `where` can filter by `tag` or `field`

    select * from <name> where <tag1> = <value>

## Import / Export

Instructions for import and export taken from [Stackoverflow](https://stackoverflow.com/questions/27779472/export-data-from-influxdb)

Export data from a running data base to a local folder.

    influxd backup -database <name> <folder>
    
Import data from a local folder to a stopped data base.

    influxd restore -metadir /var/lib/influxdb/meta <folder>
    influxd restore -database <name> -datadir /var/lib/influxdb/meta <folder>

## InfluxQL

Functions: https://docs.influxdata.com/influxdb/v1.5/query_language/functions
