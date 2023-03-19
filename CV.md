I like writing software! 

I have recently been employeed as a Solutions Architect, and as a Software Engineer.  

I enjoy exploring domains far and wide, but I like to get into the patterns too!  

Outside of my daily work, you will probably find me working on some software tooling, 
I mostly publish my recent work as Open Source to https://github.com/fabiancook or https://github.com/virtualstate

## Technical Things

> [Looking for my work experience instead? Jump there](#employment)

### Navigation API

Recently I have been working on a [Navigation API](https://github.com/virtualstate/navigation)
that implements the newest [WICG proposal for web navigation](https://github.com/WICG/navigation-api)

> The new navigation API provides a new interface for navigations and session history, with a focus on single-page application navigations.

A native implementation of the API is available in Chrome browsers today, but with this TypeScript implementation it is available in all modern JavaScript runtimes, such as Deno, Bun, Node.js, workerd, and as a polyfill for browsers. 

The API has been implemented in a way that allows for no integration with browser-like APIs by default, it allows developers to create a completely 
decoupled navigation experience similar what is available in a browser. 

Decoupled navigation can be used to build navigation experiences similar to what is available in browsers, outside of a browser
runtime. 

This work included [supporting tests](https://github.com/virtualstate/navigation/blob/17132f9caabf98ee76fad459841e9c649346921b/src/tests/examples/readme-detailed.ts#L795-L808) that matches the [Navigation API Spec examples](https://github.com/WICG/navigation-api#example-using-info) as well as an attempt at using [externally published Web Platform Tests](https://github.com/web-platform-tests/wpt/tree/master/navigation-api) and running them in [GitHub Actions](https://github.com/virtualstate/navigation/actions/runs/4436327836/jobs/7784620051#step:6:2175) 

### Sequences related things. 

I have been exploring the world of sequences for a while, initially diving into [RDF](https://www.w3.org/RDF/), [Linked Data](https://www.w3.org/standards/semanticweb/data), and [SOLID](https://solidproject.org/). 

Through this journey I explored the realm of possibilities with graphs, how information can be represented in them, and what the building blocks of these graphs were. 

I published the codebases within the [OpenNetwork GitHub Organisation](https://github.com/opennetwork), through this work I had 
implemented [RDF Dataset](https://github.com/opennetwork/rdf-dataset) in TypeScript, this implementation provides a 
way to map/filter/reduce etc. over [RDF Quads](https://rdf.js.org/data-model-spec/#quad-interface) to provide an interface to 
RDF Graphs.

While working on RDF Dataset, which is synchronous sequence based, there was functionality that called for asynchronous sequences too. 

After experimenting with various ways of tackling the problem, I had settled on [iterable](https://github.com/opennetwork/iterable/tree/next), which provided similar, if not the same functionality that RDF Dataset gave, but with compatibility for any JavaScript object that provided a sequence, including asynchronous sequences.

The pattern iterable implemented matches what is provided by JavaScript Arrays, for example map/filter/reduce. 
Eventually, unrelated to this work, [TC39 has progressed iterator-helpers through Stage 2, & 3](https://github.com/tc39/proposal-iterator-helpers) which also provides the same functionality. 

Through this work I came to the conclusion that, RDF Dataset, and similar tooling for sequences of anykind, will soon be common place natively in JavaScript runtimes.

Using the specification provided by TC39, I implemented this within the iterable package to ensure compatibility, and widen my understanding. 
There is a [synchronous version](https://github.com/opennetwork/iterable/blob/next/src/tc39/sync.ts), and [asynchronous version](https://github.com/opennetwork/iterable/blob/next/src/tc39/async.ts).

This work included [supporting](https://github.com/opennetwork/iterable/blob/next/src/tests/tc39/sync.ts) [tests](https://github.com/opennetwork/iterable/blob/next/src/tests/tc39/async.ts) that matches [the TC39 Spec examples](https://github.com/opennetwork/iterable/blob/next/src/tests/tc39/async.ts)

### JSX, Virtual State, Graphs, and KDL 

Through exploration of sequences I found myself extending the synchronous JSX model that is common place today, and including support for asynchronous sequences to be used alongside, providing a consistent interface between the two. 

With trial, error, and time, I had developed functionality to stepwise through sets of asynchronous sequences, and combine them into a single union of their values. This allowed for the further development of the JSX model, where I have made use of it to concatenate JSX fragments, components, or sequences, without needing to directly consider the individual state of each. 

Using this functionality and the JSX model, I produced a wide [range of utility](https://github.com/virtualstate/focus) [functions](https://github.com/virtualstate/focus/blob/main/src/tests/access.tsx#L65) to work with JSX. 

These utility functions lean on prior learning with sequences and includes support for [iterator-helper like functions](https://github.com/virtualstate/focus/blob/c1ca80f9cfd8304b592136514d2c8814ad5faa97/src/tests/access.tsx#L171-L183), this allows synchronous structuring of operations, but lazy execution once resolution is requested. 

A further extension of the JSX model is possible by producing further utility like tools, without changing the underlying code, functionality, or model itself. 

By stepping back from the world of visual user interfaces, and instead allowing JSX to represent any state, we can make use of JSX to produce graphs of both expected operations, and output state. 

An example of such step back is looking into [The KDL Document Language](https://github.com/kdl-org/kdl) and its similarity to JSX, so much so, that it is possible to make use of the [KDL Query Language](https://github.com/virtualstate/kdl#preparing-queries) to query JSX graphs, which shows its power when [non UI state](https://github.com/virtualstate/kdl/blob/main/src/tests/resources/setup/package.tsx#L1)

JSX may not be the correct publishing mechanism for all state, but the JSX model may be a good virtual state container to hold, label, and relate state. 

### Flow based programming 

Earlier on in my Open Source journey I worked with a startup called [Joukou](https://github.com/joukou/joukou#joukou)

> Joukou is a high level visual programming language for data that can be deployed to a cloud environment and managed remotely via a web interface. Joukou merges flow-based programming with BPMN 2.0.

Through this work, I was able to explore tools such as [fleet](https://github.com/coreos/fleet), [Docker](https://www.docker.com/), [CoreOS](https://en.wikipedia.org/wiki/Container_Linux), and expand on [flow based programming protocols](https://github.com/joukou/joukou-flow/tree/develop/src/protocols). 

Part of the overall solution was an orchestration mechanim called the [conductor](https://github.com/joukou/joukou-conductor-fleet/tree/develop) which was used to  maintain units of work to be ran within docker. 

### Communication & Networking 

Prior to entering the world of software engineering professionally I had an interest in technology and electronics. 

My earliest experience with programming was with BASIC, working with [PICAXE 08 Microcontroller](https://picaxe.com/hardware/picaxe-chips/picaxe-08m2-microcontroller/)

One set of components I had good fun with was working with any kind of transmit & receiver devices, or the "more fancy" bluetooth transmitting devices (These small microcontrollers work great with them over serial!). 

I had entered electronics competitions with the projects I had worked on throughout these years. 

Around about the same time I was learning about networking, having access to a complete Cisco network lab and a great mentor I learned a lot about general networking systems, including configuring devices and the theory behind it. 

Which leads to my first introduction to professional software, which nicely fits into the communication theme, but slightly different. 

My first role, I was tasked with developing an Android Application that could be used in remote parts of the world, such as remote parts of the Sahara, or a forest, where the application would be used offline to capture information from tracking devices placed on animals for research, such as understanding their migration patterns. 

The application utilised serial communication similar to the microcontrollers I had already had experience with. 

Once the researcher was within range of an internet connection, the data could be uploaded to the primary collection services for analysis and processing, enabling a true sneakernet research effort. 

-------------

Napier, New Zealand

[hello@fabiancook.dev](mailto:hello@fabiancook.dev)

[linkedin.com/in/fabian-cook/](https://www.linkedin.com/in/fabian-cook/)

[github.com/fabiancook](https://github.com/fabiancook)

## Employment

### Datacom (2022 - )

#### Summary 

Lead Solution Architect focused on Research & Analysis of a large scale multi-country system.

### Dovetail (2022)

#### Summary 

Software Engineering focused on designing and developing a authorization rules engine.

#### Authsignal

[authsignal.com](https://www.authsignal.com/)

- Node.js authorization rules engine

### Clearpoint (2021 - 2022)

#### Summary 

Lead Front End Engineer role supporting teams working on React, and React Native codebases,
transitioned to Senior Software Engineer widening view to include Node.js engineering. 

#### Contact Energy

- Service onboarding tooling

  _TypeScript, React_
  
- Pair mentoring
- Frontend team leadership

### Cloudswept (2018 - 2020)

_Senior Software Developer, Full Stack, Primary: Backing Services_

#### Summary

Full stack development role using Node.js, TypeScript, Java, MongoDB, React, and React Native. 

#### Projects

- Medical questionnaire tracking mobile application

  _JavaScript, Angular 2, Cordova_

- Location tracking mobile application and related services

  _Node.js, AWS Lambda, MongoDB, React, and React Native_

- Financial reporting services

  _Node.js, AWS Lambda, Java, JavaScript, Java Spring, MongoDB, and React_

- Environment reporting dashboards and services 

  _Node.js, AWS Lambda, JavaScript, MongoDB, and React_

- Human resource management and reporting

  _Node.js, AWS Lambda, TypeScript, MongoDB, React, and React Native_

- Process management

  _Node.js, AWS Lambda, TypeScript, MongoDB, React Native, and React_

### NZ Digital (2016 - 2018)

_Lead Software Developer, Full Stack, Primary: Backing Service_

[nzdigital.co.nz](https://nzdigital.co.nz)

#### Summary

Full stack development role using Node.js, MongoDB, and React. Primary development was around bespoke business apps. 

#### Projects

- Report generation

  _Node.js, Heroku, AWS Lambda, MongoDB, and Angular_

- Enterprise blog mobile application and admin interface

  _Node.js, Heroku, MongoDB, React, and React Native_

- Enterprise blog website

  _Wordpress, PHP, JavaScript_

- Process management

  _Node.js, Heroku, MongoDB, React Native, and React_

- Property management

  _Node.js, Heroku, MongoDB, and React_

- Flight management

  _Node.js, Heroku, MongoDB, and React_

- Subscription ordering and management

  _Node.js, Heroku, MongoDB, and React_

- Factory ordering and processing 

  _Node.js, Heroku, MongoDB, and React_

- Regional health information blog platform for practitioners   

  _Node.js, Heroku, MongoDB, and React_

### NOW NZ (2015 - 2016) 

_Software Developer, Full Stack, Primary: Backing Services_

[nownz.co.nz](https://nownz.co.nz)

#### Summary

Full stack development role using Node.js, including development of multiple integration services for credit checking and broadband provisioning.

#### Projects

- Prequalification and Ordering Integration (Chorus Wireline, Chorus NGA, and Unison)

  _Node.js, Phantomjs, SOAP, and MongoDB_

- Credit checking (Veda, now Equifax) integration and rules engine

  _Node.js, Heroku, and MongoDB_

- Order management

  _Node.js, Heroku, MongoDB, and Angular_

### Joukou (2014)

_Software Developer, Full Stack_

[github.com/joukou](https://github.com/joukou )

#### Summary

Full stack development focused on deployment of a visual functional programming language or flow based programming (FBP) to the cloud. Used React rendering to SVG for the flow based programming interface and AngularJS for the wider application. All code for the Joukou project is freely available on GitHub (https://github.com/joukou).

#### Projects

- Flow based user Interface 

  _CoffeeScript, Angular, React (0.x)_

- Flow based programming protocol

  _Node.js, Digital Ocean, CoffeeScript, Riak_

- Docker node management service

  _Node.js, Digital Ocean, CoffeeScript, Docker, Riak_

### Fastway Global (2012 - 2014), now Aramex

_Software Developer, Full Stack_

[aramex.com](https://www.aramex.com)

#### Summary 

Full stack development role focused primarily on the .NET framework, working on a variety of projects. 

#### Projects

- Customer user interface and components 

  _.NET, C#, ASP.NET, JavaScript, CSS, and MSSQL_
- Customs shipping integration

  _.NET, C#, and MSSQL_
- Onsite order processing and label printing

  _.NET, and WinForms_

### Sirtrack (2012), now Lotek

_Software Developer, Full Stack_

[lotek.com](https://www.lotek.com/) 

#### Summary 

Android development role, focused on bluetooth communication with embedded devices

#### Projects

- In field download of tracking collar data

  _Android, Java, Bluetooth, USB Serial_

## Publications

### Node.js Essentials

_ISBN 13: 9781785284922, no longer in print_

Node.js development book focusing on the fundamentals. Demonstrates how to use Express, Socket.IO, & MongoDB.

## Other Contributions

### Virtual State

[github.com/virtualstate](https://github.com/virtualstate)

Open source software focused on developer experience

- Software Developer

### Open Network

[github.com/opennetwork](https://github.com/opennetwork)

Open source software focused on peer to peer tooling

- Software Developer

### JavaScript New Zealand

[javascript.org.nz/](https://javascript.org.nz/)

- Society Treasurer, 2019 - 2020
- Society President, 2020 - 
