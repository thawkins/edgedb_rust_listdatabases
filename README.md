# edgedb-rust simple sample code

## Overview

This example project is a very simple implementaion of a rust project that connects to and renders data from an edgedb database. 

It is should to be considered a "Hello world" example for connecting to the DB system in rust. 

The application is a standalone version of the list-databases example code from the edgedb-client project 

[https://github.com/edgedb/edgedb-rust](https://github.com/edgedb/edgedb-rust)

This code is property of the edgedb team and no rights are reserved by its use here. the sample is a convience for helping others get started. 
## Prerequisits

This sample assumes that you have the following items installed

1. Rust language [Installing Rust](https://www.rust-lang.org/tools/install)
2. EdgeDb [Installing edgedb](https://www.edgedb.com/install)
3. On debian based distros you will need add the cc compliler and friends with 
``` apt-get install build-essential```


## Building and running 

### Setting up

1. Check out the code to a local folder
2. Change into that folder
3. Run the folowing
``` edgedb project init ```
4. Run ```edgedb ui``` and add the sample mcu movies data

### Building (debug version)
1. Change to the root of the project
2. Build with ```cargo build```

### Building (release version)
1. Change to the root of the project
2. Build with ```cargo build --release```

### Running (debug version)  
After a successfull build you can run the sample by: 

1. Change to the root of the project
2. execute the command ```./target/debug/edgedb_rust_listdatabases```
3. The result should be 

```
$./target/debug/edgedb_rust_listdatabases 
Database list:
edgedb
_example
$ 

```

It may take a long time the first time you execute it, as it may have to start up the edgedb database if it has not already started, it is a feature of edgedb V2.0 that it will autostart the database server when it is first accessed via its socket. 

You may get the following error message if that startup takes longer than 30 seconds which is the default timeout value for the client. This should only happen if you are working on a slow machine. 

```
$./target/debug/edgedb_rust_listdatabases 
Error: Error(Inner { code: 4278255872, messages: ["cannot establish connection for 30s"], error: Some(Kind(TimedOut)), headers: {} })
$
```

### Running (release version)   
1. Change to the root of the project
2. execute the command ```./target/release/edgedb_rust_listdatabases```
3. results should be the same as per the debug version

