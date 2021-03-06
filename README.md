# WinApi.Demo
Simple demo project showing off capabilities of Windows API in internet connection via HTTP requests, RPC and WebSockets.
Feel free to download the source code and use as a guide in your projects.

[Click here](https://github.com/Maissae/WinApi.Demo/archive/master.zip) to download source code!

## HTTP Requests
Done in C# with `wininet` and PInvoke. Signatures are contained in `lib/WinApi.Demo.Signatures/Wininet.cs`. 
Library is loaded during runtime of the application and based on the signatures, methods are called from it.
Application has limited capabilites but it is able to do simple HTTP operations such as `GET`, `POST`, `PUT` and `DELETE`.
With application also comes simple API that can be used for testing the calls.

## WebSockets
Done in C# as well with `ws2_32` and PInvoke. You can find functions signatures in `lib/WinApi.Demo.Singatures/Ws2_32.cs`.
Just like above library is loaded during the runtime of application and methods are called based on the declared signatures.
As for application it is a simple chat that can be used over network.
It requires a server that handles a communication between all the users, it's included into projects as well.
Server can handle multiple users as for each one of them thread is created.
It'll broadcast a message to all users that are connected to it.

## RPC
Done in C++ using multiple Windows API libraries related to RPC model. 
The `WinApi.Demo.Rpc.Core` project demonstrates how one can generate files containing the client stub, the server stub and the common interface shared by both the RPC client and the RPC server. Those files are being generated by MIDL compiler which analyzes `.idl` and `.acf` configuration files which are contained in the project's root directory.
The `WinApi.Demo.Rpc.Server` project presents the most simple way in which RPC server application can be set up. It implements the methods defined in the common interface which can be invoked by its clients, contains its default configuration (used protocol, IP address, number of working threads, etc.) and executes code that makes it listen for incoming RPC requests. 
The `WinApi.Demo.Rpc.Client` project shows a basic RPC client application. It performs some initial configuration setup and then invokes the method defined in the common interface, therefore sending a RPC request to the server.
