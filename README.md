# React Router Dom v6 Route path matching issue

This repository demonstrates a bug in React Router Dom v6 where the routes only match the root path ('/') and display the 404 component for all other paths.  The expected behavior is for the routes to correctly match the specified paths ('/about').

## Bug Description

Routes renders 404 component for every path except the root path ('/') even when the paths ('/about') are defined correctly.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe that only the root path ('/') works correctly. Any other path renders the 404 component.

## Solution

The issue lies in how the routes are defined. It's necessary to add the `exact` prop to each route in order to properly match the given path. Otherwise, the catch-all route (`path="*"`) will take precedence and always render the 404 component.