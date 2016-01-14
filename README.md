# KIARA - FIWARE Advanced  Middleware

This is the ICCLab KIARA Webrepository for the full version of this page please go to the [KIARA Github webpage](http://icclab.github.io/KIARA).

KIARA Github repository: [https://github.com/FIWARE-Middleware/KIARA](https://github.com/FIWARE-Middleware/KIARA)

KIARA full Documentation: [Read The Docs](http://fiware-middleware-kiara.readthedocs.org/)

## Overview

KIARA Fiware Advanced Middleware is a Java based communication middleware for modern, efficient and secure applications. It is an implementation of the FIWARE Advanced Middleware Generic Enabler (GE). 

The Advanced Middleware GE is a set of compile-time and run-time tools, and a communication library to be integrated with the application. Thus, the requirements are rather minimal. In particular it requires no service running in the background.

KIARA implements transparent, fast, secure and standard conform communication between applications or services running on multiple machines using different Operating Systems. It also provides a friendly and extensible API.

The [FIWARE platform](http://www.fiware.org) offers a powerful set of components (Generic Enablers) providing APIs (Application Programming Interfaces) that ease the development of Smart Applications in multiple vertical sectors.

The [FIWARE catalogue](http://catalog.fiware.org) contains a rich library of reference implementations of the components (Generic Enablers) that allow developers to implement functionalities such as the connection to the Internet of Things or Big Data analysis, making programming much easier.

## Features

This first release focuses on the basic features of RPC and Publish/Subscribe communication:

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

- [Download .zip file](https://github.com/FIWARE-Middleware/KIARA/zipball/master)
- [Download .tar.gz file](https://github.com/FIWARE-Middleware/KIARA/tarball/master)

## Community & Support
To report bugs or request features, submit issues [here on GitHub](https://github.com/fiware-middleware/KIARA/issues). For additional resources, you can contact the maintainers directly. For general questions and discussions please use the KIARA-discuss mailing list. Once you [subscribe](https://mailman.engineering.zhaw.ch/mailman/listinfo/icclab-KIARA) to the list, you can send mail to the list address: [icclab-KIARA@dornbirn.zhaw.ch](mailto:icclab-KIARA@dornbirn.zhaw.ch). The mailing list archives are also [available on the web](https://mailman.engineering.zhaw.ch/pipermail/icclab-KIARA/).

And of course you can follow us on the [ICCLab blog](https://blog.zhaw.ch/icclab) for news and updates.

### License

KIARA is licensed under the [Lesser GNU Public License (LGPL)](http://www.gnu.org/licenses/lgpl.html).

### Provided by
[![ICCLab Logo](./docs/img/icclab_logo_300x100.png "ICCLab")](https://blog.zhaw.ch/icclab)

### in colaboration with
[![FIWARE Logo](./docs/img/FIWARE_logo_60.png "FIWARE")](http://fiware.org)
[![eProsima Logo](./docs/img/eProsimaLogo_60.png "eProsima")](http://www.eprosima.com)
[![DFKI Logo](./docs/img/DFKI_Logo_60.png "DFKI")](http://www.dfki.de)

### Supported by
[![EU FP7 Logo](./docs/img/EU_FP7_logo.png)](http://cordis.europa.eu/fp7/home_en.html)
