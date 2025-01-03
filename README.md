# Astah plugin ideas

The following repository contains all the ideas that we came up for Astah, a great modeling tool. If you would
like to implement any of these ideas, feel free to contact me, I am happy to support you.

## Import schema structure from SQL database

Import schema structure from an SQL database into Astah.

## UML Profile editor plugin [done]

- See: https://github.com/modeldriven-hu/astah-profile

Currently Astah SysML is not able to create custom profiles with tags, only internal profiles, however, it is able to import external profiles.
One way to create a profile is to use Eclipse UML, described on the following page: 

https://wiki.eclipse.org/MDT/UML2/Introduction_to_UML2_Profiles

It would be beneficial to have the profile editing capability inside Astah, instead of needing to open a 3rd party tool.

- [X] Create a new profile
- [X] Load profile from file
- [X] Save profile to file
- [X] Add stereotypes to the profile
- [X] Set metaclass for stereotypes
- [X] Add tags to stereotypes
- [X] Set type for a tag
- [X] Able to update a model file with changes, handle only addition, and not removal

## Diagram helper plugin [done]

- See: https://github.com/modeldriven-hu/astah-easy-diagram

Everyone hates pixel pushing, it makes modeling so not fun. Let's make it more fun!

- Straighten line (remove additional point, keep only the start and end point)
- Input coordinates (display x,y coordinate, width and height, and allow modification of it by entering new values. Could keep also aspect ratio. Also could keep connection points.
- Snap to pixel
  
## Rich text editor [partially done]

- See: https://github.com/modeldriven-hu/astah-rich-document

For documenting model elements Astah only provides a text area. In this plugin, when the user select a model element, the
associated documentation would be visible in the rich text editor. When the user deselects a model element, then it the 
editor will be empty and disabled. When user selects multiple elements, the editor will be likewise empty and disabled.

Functions:
- [x] bold
- [x] italic
- [x] align (left, right, center, justify)
- [x] color (background, foreground)
- [ ] list
- [ ] numbering
- [ ] table
- [ ] link
- [ ] image?
- [ ] undo/redo support
- [ ] etc.

## Legend [done]

-See: https://github.com/modeldriven-hu/astah-legend

In some diagrams we would like to color certain elements based on certain rules. The plugin could do the following:

- Define legend (name and legend items)
- Define legend item (text color, background color, etc. and the rule)
- Allocate a legend to one or multiple diagrams
- See which legends are allocated to the diagram
- Apply legend on the diagram

## Plugin manager and plugin server

In a corporate environment it is really difficult to distribute plugins. The plugin manager allows users to download plugins
from a configured repository on demand.

Functions:
- Server hosts plugin bundles
- Configure multiple plugin servers / repositories
- Nexus? Reposilite? 
- List plugins
- Search for plugin
- Filter plugins by type
- Notify user when a new version of an installed plugin is available
- Check digital signature before install
- Use some well defined repository as source
- etc.

## OpenAPI import [done]

- See https://github.com/modeldriven-hu/astah-openapi

When working with software systems often we need to integrate with API-s described in a form of OpenAPI (Swagger) specification. The 
OpenAPI import plugin would import an OpenAPI specification into the model.

Functions:
- OpenAPI file selector
- List available endpoints, allow selection only a subsets of endpoints
- Create interfaces, operations, requests, responses, etc.
- Customization: which is the counterpart of an OpenAPI concept (stereotype, etc.)

## Generic table

We often need to list certain model elements and filter among them. The plugin would allow to display a list of elements of a certain 
type in a form of a table, probably under a package. 

Functions:
- List elements of a certain package
- Select columns
- Filter elements based on a rule (groovy?)
- Find element in tree
- Create new model element (for example requirement)
- Export to CSV/Excel

## Statistics [partially done]

Display statistics of the model. Number of model elements, by type, number of diagrams, by type, etc.

Partially done as part of the Easy Diagram Plugin.

## OSLC support

This is a challenging but super interesting task. Add OSLC client support to Astah so that a connection to an OSLC server could
be built up. A good starting point could be an integration to requirements part of the following reference implementation:  
https://github.com/oslc-op/refimpl

## Model import without Astah [POC done]

- https://github.com/modeldriven-hu/astah-xmi

Being able to offline import a model and run for example validation rules on it. It would be great if we could put a model in a
CI/CD environment and have a git hook to run verification / model transformation.

## HTML generation [Done]

- Part of the model server solution

Export a document into a HTML.

## Model server [In development]

- The MVP is done
- Currently allows to upload models and share them on a web based interface for registered users
- Will be commercially available in 2025
- Additional features like the ones described below might be added later

A model server could get a model file and serve it to various interfaces. OSLC, REST, etc. 
It could also support locking/version management.

## Text based modeling capability with LLM support

The idea is to extend Astah SysML with a text based syntax (similar to PlantUML) that is more familiar to developers. This might be also combined with some AI/LLM capabilites. The idea is that they can quickly create a preview diagram and then transform it into a real model structure.

