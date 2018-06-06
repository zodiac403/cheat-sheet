# Influx CLI Cheat Sheet

## Connect

Connect the client to the data base. `-precision` specifies the time stamp format for query results.

    influx -precision rfc3339

Connect to a data base running on a specific host (default values are host `localhost` and port `8086`)

    influx -host <host> -port <port> -precision <precision>

## Data Base

Show available data bases

    show databases

Create a data base

    create database <database>

Set the data base for further requests

    use <database>

Drop data base

    drop database <database>

## Measurements

Show available data bases

    show measurements

Drop (delete) measurement from database

    drop measurement <measurement>

## Values

Insert an entry to the database. The number of tags and files may vary. If `time` parameter is ommited, Influx uses the current time.

    insert <measurement>,<tag1>=<value>,<tag2>=<value> <field1>=<value>,<field2>=<value> <time>

Query all values for a measurement

    select * from <measurement>

Query and filter values for a measurement. `where` can filter by `tag` or `field`. Combine multiple tags and fields with `and` or `or`.

    select * from <measurement> where <tag1>=<value>

## Import / Export

Instructions for import and export taken from [Stackoverflow](https://stackoverflow.com/questions/27779472/export-data-from-influxdb)

Export data from a running data base to a local folder.

    influxd backup -database <name> <folder>
    
Import data from local `folder` to a stopped data base. Values for `metadir` and `datadir` must be Influx persisting directories:
* Linux
    ```
    influxd restore -metadir /var/lib/influxdb/meta <folder>
    influxd restore -database <name> -datadir /var/lib/influxdb/data <folder>
    ```

* Windows
    ```
    influxd restore -metadir %USERPROFILE%/.influxdb/meta <folder>
    influxd restore -database <name> -datadir %USERPROFILE%/.influxdb/data <folder>
    ```
## InfluxQL

Functions: https://docs.influxdata.com/influxdb/v1.5/query_language/functions
