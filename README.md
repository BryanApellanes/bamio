# This document is a draft

TODO: https://natemcmaster.com/blog/2017/11/11/build-tools-in-nuget/

# Bamdb

Bam Database (bamdb) is a high level data access component which provides a client gateway to multiple data persistence layers including various RDBM systems such as Microsoft Sql, MySql, Postgres and SQLite as well as no sql solutions such as mongo and its own internal data repository system.  It is also used to generate data access objects, data transfer objects and repositories from plain CLR classes.

## Command Line Switch Code Generation
The following describes command line switch based code generation options using bamdb.

### /generateDaoAssemblyForTypes
Generate a Dao Assembly for types in a specified namespace of a specified assembly.

### /generateDaoCodeForTypes
Generate Dao source code for types in a specified namespace of a specified assembly.

### /generateDtosForDaos
Generate Dto source for types in a specified namespace of a specified assembly, optionally compiling and keeping the source.

### /generateSchemaRepository
In addition to generating Daos and Dtos for types in a specified namespace of a specified assembly, `/generateSchemaRepository` switch generates a schema specific DaoRepository which can store all the types found.

Accepts a `config` command line argument specifying the path to a yaml serialized GenerationConfig:

```
bamdb /config:<pathToConfig>
```

An example of a DaoRepoGenerationConfig.yaml file:

```yaml
SchemaName: MyApplicationSchema
WriteSourceTo: /tmp/MyApplicationSchema
TypeAssembly: /tmp/bin/myapplication.dll
FromNameSpace: My.Application.Data
ToNameSpace: My.Appliction.Data.Dao
```

Alternatively, each option can be specified on the command line, note that command line options are case sensitive:

```
bamdb /schemaName:MyApplicationSchema /writeSource:C:\tmp\MyApplicationSchema /typeAssembly:C:\bin\myapplication.dll /fromNameSpace:My.Application.Data /toNameSpace:My.Application.Data.Dao
```

## BamDb Schema File
A bamdb schema file is a json formatted file containing meta data that describes a database table structure and relationships.

## Database Server

The following describes the options available to serve data using bamdb.




 