---
layout: default
title: Concurrent Programming 2
---

# Lab6 : Data Center (Asyncrhonous Message passing)

A computer center has two printers, A and B, that are similar but not identical. Three kinds of client processes use the printers: those that must use printer A, those who must use printer B, and those who can use either A or B. All synchronizing and communication is done via asynchronous message passing (`send` and `receive`).

A client needing a printer sends a request to an allocation server, who sends the next possible available printer to the client; the client then "prints"  its file to the printer by calling the printer's "print" method (**one line at a time**); a message is sent to the server when printing is completed. The client waits randomly before attempting to print the next file.

The program will be invoked as follows:
```bash
jrgo <client parameters> <file parameters> <machine parameters>
````
where `client parameters` are, in order

* `nb_ClientA`:  the number of users that must use printer A  (default value: 19)
* `nb_ClientB`:  the number of users that must use printer B  (default value: 13)
* `nb_ClientAB`: the number of users that can use either A or B  (default value: 29)

`file parameters` are, in order

* `nb_files`: the maximum number of files that a client will print.  A client randomly picks a number between 1 and nb_files (inclusive) which will be the number of files that a client will print (default value: 11)
* `nb_lines`:  the maximum number of "lines" a file has.  For each file, a client selects a number randomly between 1 and nb_lines (inclusive) to send to the printer for printing (default value: 43)

`machine parameters` are, in order

* `mach_Server`: the location of the machine where the server is located (default: localhost)
* `mach_PA`:     the location of the machine where printer A is located (default: localhost)
* `mach_PB`:     the location of the machine where printer B is located (default: localhost)
* `mach_clients`: A list of machines where the clients are located (default: all are located on the same machine, localhost) 


You must distribute the clients "as evenly as possible" across the listed machines. For example, if there are 5 client machines (and all other parameters have their default values), then  I would expect all machines except one will contain 12 clients.  Output lines from the clients look like this:

`Client_<client type> #<client No>, file <file No>, line <line No>`

for example

`Client_AB #1, file 3, line 20`

You are free to add additional information.

Each printer "prints" its output in its own file.  The output filenames (**do not use absolute filenames**!) for the printers are

`printer<type>_<your user name>`, e.g.  &rarr;  `printerA_john.doe`

The name of the main class is **`printServe`**

## Implementation steps

There will be 2 development stages:  in stage 1 there are no virtual machines, all processes are located in a single virtual machine. Once you have tested and are satisfied that everything works, you place a comment in CVS stating which versions of your files work in a single virtual machine before proceeding to making all work with virtual machines.

**Advice**:  Clients should know as little as possible about the printers;  the print server just sends a client requesting a printer a capability which enables the client to print to that printer.

### Data structures

About the data structures you will be using:  if you want to use "special" data structures or containers in your program (other than the basic data types and arrays), I will want a comment justifying how the use of  the data structure is necessary as opposed to a simple array. 

Your program must be checked latest on April 9th, 2020.
