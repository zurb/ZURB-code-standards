# Libraries

These are the libraries that comprise the Foundation family.

## Frameworks

### Foundation for Sites

Framework for creating responsive websites. First launched in 2011, currently on version 6.

### Foundation for Apps

Framework for creating responsive web apps. First launched in 2014, currently on version 1. Powered by AngularJS.

### Foundation for Emails

Framework for creating responsive HTML emails. First launched in 2013, currently on version 2. Powered by a custom templating engine.

## Libraries

### Supercollider

A documentation generator that pulls in documentation from Markdown files, JSDoc, and SassDoc, and compiles it into a series of HTML files using Handlebars templates.

**Used by:** Sites, Apps, Emails

### Motion UI

Sass library for creating custom transitions and animations. Includes a pre-build set of transitions derived from five fundamental motions: slide, fade, spin, hinge, and scale. Also includes a suite of tools for creating hybrid animations, and sequencing animations.

**Used by:** Sites, Apps

### Inky

A templating language that compiles to HTML. Used by Foundation for Emails to abstract its complex table-based syntax into something more friendly. Distributed as a standalone library and as a Gulp plugin.

**Used by:** Emails

### Flat File Compiler

Gulp plugin that processes HTML pages, and compiles them with a common template. Can be extended with Handlebars partials, data, and helpers.

**Used by:** Sites, Emails

### Foundation CLI

A Node-powered command line tool to quickly create new Foundation projects.

**Used by:** Sites, Apps, Emails

### Launcher

A graphical wrapper for the Foundation CLI. Built with Angular and Foundation for Apps, housed by Electron, and distributed for Windows, OS X, and Linux.

**Used by:** Sites, Apps, Emails

### Front Router

Gulp plugin that converts Front Matter on Angular templates to a JavaScript object, which is consumed by a Foundation for Apps module that generates ui-router-compatible routes. Helpful for quickly prototyping web apps without needing to write JavaScript.

**Used by:** Apps

### Settings Parser

Node- and SassDoc-powered parser that aggregates settings variables from Sass files, and compiles them into one finished file. Used to streamline the process of modifying settings variables.

**Used by:** Sites, Apps, Emails
