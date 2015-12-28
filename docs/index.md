# KIARA - FIWARE Advanced  Middleware

## Overview

KIARA Fiware Advanced Middleware is a Java based communication middleware for modern, efficient and secure applications. It is an implementation of the FIWARE Advanced Middleware Generic Enabler (GE). 

The Advanced Middleware GE is a set of compile-time and run-time tools, and a communication library to be integrated with the application. Thus, the requirements are rather minimal. In particular it requires no service running in the background.

KIARA implements transparent, fast, secure and standard conform communication between applications or services running under different machines and using different Operating Systems. It also provides the users with a friendly and extensible API.

The [FIWARE platform](http://www.fiware.org) provides a rather simple yet powerful set of APIs (Application Programming Interfaces) that ease the development of Smart Applications in multiple vertical sectors.

The [FIWARE Catalogue](http://catalog.fiware.org) contains a rich library of components (Generic Enablers) with reference implementations that allow developers to put into effect functionalities such as the connection to the Internet of Things or Big Data analysis, making programming much easier.

## Features

This first release focuses on the basic features of RPC communication:

- Easy to use and extensible Application Programmer Interface (API).
Synchronous and Asynchronous function calls.
- Modern Interface Definition Language (IDL) → based on Corba IDL.
    - OMG compliant
    - Extended primitive types.
- IDL derived operation mode for the RPC Client/Server communication pattern
    - By generating Stubs and Skeletons at compile time → RPC API
    - By using proxies to provide and call the functions at runtime → RPC Dynamic Types API
- IDL derived operation mode for the Publish/Subscribe communication pattern
- TLS encryption for secure communication

## Roadmap

Upcoming versions will include additional features:

- Advanced security features like field encryption and authentication
- Application derived and mapped operation mode providing dynamic declaration of functions and data type mapping in source code. 

## Getting started

### Hello World Video

The following video shows a basic Hello World implementation using KIARA. For more details see the [example](#a-quick-example) below or check the [documentation](#documentation) section.

<iframe width="720" height="405" src="https://www.youtube.com/embed/EJjMSOjwu2s" frameborder="0" allowfullscreen></iframe>

### A quick example

In the IDL derived approach, first the IDL (Interface Definition Language) definition of the remote functions has to be created:

```
service Calculator {
     float32 add (float32 n1, float32 n2);
     float32 subtract (float32 n1, float32 n2);
};
``` 

The developer has to implement the server side functions of the class `CalculatorServantImpl`:

```java
public static class CalculatorServantImpl extends CalculatorServant
{
     @Override
     public float add (/*in*/ float n1, /*in*/ float n2) {
          return (float) n1   n2;
     }
 
     @Override
     public float subtract (/*in*/ float n1, /*in*/ float n2) {
         return (float) n1 - n2;
     }
     ...
}
```

Now the server can be started:

```java
// Create context, server and service
Context context = Kiara.createContext();
Server server = context.createServer();
Service service = context.createService();

// Create and register an instance of the CalculatorServant implementation.
CalculatorServant Calculator_impl = new CalculatorServantImpl();
service.register(Calculator_impl);

// register the service on port 9090 using CDR serialization 
server.addService(service, "tcp://0.0.0.0:9090", "cdr");

// run the server
server.run();
```

The client can connect and call the remote functions via the generated proxy class:

```java
// Create context
Context context = Kiara.createContext();

// setup the connection to the server
Connection connection = context.connect("tcp://192.168.1.18:9090?serialization=cdr");

// get the client Proxy implementation
CalculatorClient client = connection.getServiceProxy(CalculatorClient.class);

// Call the remote methods
float result = client.add(3, 5);
```

## Documentation

Find the full documentation on [Read The Docs](http://fiware-middleware-kiara.readthedocs.org/):

- [Installation and Administration Guide](http://fiware-middleware-kiara.readthedocs.org/en/latest/manuals/Installation_and_Admin_Guide.html)
- [User and Programmer Guide](http://fiware-middleware-kiara.readthedocs.org/en/latest/manuals/User_and_Programmer_Guide.html)
- [Open Specification](http://fiware-middleware-kiara.readthedocs.org/en/latest/specification/OpenSpecification.html)
- API Specifications:
    - [RPC API Specification](http://fiware-middleware-kiara.readthedocs.org/en/latest/specification/Middleware_RPC_API_Specification.html)
    - [RPC Dynamic Types API Specification](http://fiware-middleware-kiara.readthedocs.org/en/latest/specification/Middleware_RPC_Dynamic_Types_API_Specification.html) 
    - [Publish/Subscribe API Specification](http://fiware-middleware-kiara.readthedocs.org/en/latest/specification/Middleware_PUBSUB_API_Specification.html)
    - [IDL Specification](http://fiware-middleware-kiara.readthedocs.org/en/latest/specification/Middleware_IDL_Specification.html)

## Download

KIARA is implemented as a Java Library and published on [Maven-Central](http://search.maven.org/#search|ga|1|g:org.fiware.kiara). It can be used with every modern build management tool like [Maven](https://maven.apache.org) or [Gradle](https://gradle.org).
For basic usage please check our [Installation Manual](http://fiware-middleware-kiara.readthedocs.org/en/latest/manuals/Installation_and_Admin_Guide.html) and [User Guide](http://fiware-middleware-kiara.readthedocs.org/en/latest/manuals/User_and_Programmer_Guide.html).

To download the source code check out the [KIARA Github repository](https://github.com/FIWARE-Middleware/KIARA) or download the archive:

<button href="https://github.com/FIWARE-Middleware/KIARA/zipball/master" class="download">
    <small>Download</small>.zip file
</button>
<button href="https://github.com/FIWARE-Middleware/KIARA/tarball/master" class="download">
    <small>Download</small>.tar.gz file
</button>


## Community & Support
To report bugs or request features, submit issues [here on GitHub](https://github.com/fiware-middleware/KIARA/issues). For additional resources, you can contact the maintainers directly. For general questions and discussions please use the KIARA-discuss mailing list. Once you [subscribe](https://mailman.engineering.zhaw.ch/mailman/listinfo/icclab-KIARA) to the list, you can send mail to the list address: [icclab-KIARA@dornbirn.zhaw.ch](mailto:icclab-KIARA@dornbirn.zhaw.ch). The mailing list archives are also [available on the web](https://mailman.engineering.zhaw.ch/pipermail/icclab-KIARA/).

And of course you can follow us on the [ICCLab blog](https://blog.zhaw.ch/icclab) for news and updates.

### License

KIARA is licensed under the [Lesser GNU Public License (LGPL)](http://www.gnu.org/licenses/lgpl.html).

### Provided by
[![ICCLab Logo](./img/icclab_logo_300x100.png "ICCLab")](https://blog.zhaw.ch/icclab)

### in colaboration with
[![FIWARE Logo](./img/FIWARE_logo_60.png "FIWARE")](http://fiware.org)
[![eProsima Logo](./img/eProsimaLogo_60.png "eProsima")](http://www.eprosima.com)
[![DFKI Logo](./img/DFKI_Logo_60.png "DFKI")](http://www.dfki.de)
