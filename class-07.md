# APIs continued

[Home](https://sayefdeen.github.io/reading-notes301/)

## HTTP

HTTP stands for Hyper Text Transfer Protocol, it describe the location of something anywhere in the world from anywhere in the world, you can think of it like the GPS coordinates for knowledge and information.

The whole world wide web is built on an architectural style called “REST”. REST provides a definition of a “resource”, which is what those things point to.

## URL

The URL tell the browser that there's a concept somwhere, A browser can then go ask for a specific representation of the concept, specifically the browser asks for the web page representaion of the concept.

## API's

The basic concept of an API is that a machine could use the web just like people do, computers can send those same protocoles to send messages back and forth to each other.

## Polymorphism

It's a way of saying that different nouns can have the same verb applied to them, for instance when you go to a web page the browser dose an HTTP GET on the URL you type in and back comes a web page.

some types of noun i can GET:

- Images
- text
- Video
- Mp3
- slideshow

You can GET all of them the same way given a URL.

Most universal verbs are GET,PUT,and DELETE

Every URL would have a human readable and a machine readable representation. When a machine GETs the resource, it will ask for the machine readable one (Data). When a browser GETs a resource for a human (layout and styling), it will ask for the human readable one.

Each of the systems would retrieve information from each other using a simple HTTP GET. If one system needs to add something to another system, it would use an HTTP POST. If a system wants to replace something in another system, it uses an HTTP PUT, or, to do a partial update, it'll hopefully use PATCH
