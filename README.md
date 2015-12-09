json-rpc-stomp-simple
===========================

This is an implementation of JSON-RPC 1.1/2.0 over STOMP (https://stomp.github.io/) protocol in Perl and PHP. It's firstly designed to work with ActiveMQ Broker version 5.2 or more.

Why i create this
-------------------------

The main reason of this implementation because i need a simple, effective RPC method for a scripting web environment (from Perl and PHP),
that supports asynchronous/synchronous call, free schema model, and the server can be mixed existing system and new's in any language.

Most implementations of JSON-RPC are over HTTP transport, that only supports a synchronous request/response scheme to single URI.
It's not scalable enough for thousands of clients and thousands calls per second. So my choice is Stomp - a text-based message protocol -
as the transport for the JSON-RPC.

I use it for both PHP and Perl, PHP is web front-end (presentation, form and input validation - actually it replaces an old mod_perl front-end),
makes calls function to the back-end processes (bussiness processing, a lot modules already written in Perl). The back-end
system connects to the Database (Oracle) to store/retrieve the data (that is difficult to use PHP, but Perl with DBD::Oracle).

Main features
--------------------------------
JSON-RPC-Simple works very fast, supports synchronous or asynchronous. It provides reliable RPC call between scripting environment
and expose services as "Queue Name" and Its' "Method"s. Due to JSON is a free schema model, JSON can serialize/deserialize a
hash/associate arrays of Perl/PHP as parameters and returns, very easily, the solution is very flexible and more friendly
with scripting environment.

Helping by ActiveMQ infrastructure or any Stomp Message Broker, you can make a completely high available, load balancing, distributed system. 

To do
--------------------------------
I moved this project from Google code https://code.google.com/p/json-rpc-stomp-simple/. I intent to create one supports Node.Js, Node.JS
is very friendly with JSON and powered with event-style coding. Node.JS Apps can utilize lot of written Business Perl modules.
