# Astah plugin ideas

The following repository contains all the ideas that we came up for Astah, a great modeling tool. If you would
like to implement any of these ideas, feel free to contact me, I am happy to support you.

## UML Profile editor plugin

Currently Astah SysML is not able to create custom profiles with tags, only internal profiles, however, it is able to import external profiles.
One way to create a profile is to use Eclipse UML, described on the following page: 

https://wiki.eclipse.org/MDT/UML2/Introduction_to_UML2_Profiles

It would be beneficial to have the profile editing capability inside Astah, instead of needing to open a 3rd party tool.

- Create a new profile
- Load profile from file
- Save profile to file
- Add stereotypes to the profile
- Set metaclass for stereotypes
- Add tags to stereotypes
- Set multiplicity for a tag
- Set type for a tag
- Validate profile according to Astah rules (or don't even allow a creation of wrong profiles)


## Diagram helper plugin

Everyone hates pixel pushing, it makes modeling so not fun. Let's make it more fun!

- Straighten line (remove additional point, keep only the start and end point)
- Input coordinates (display x,y coordinate, width and height, and allow modification of it by entering new values. Could keep also aspect ratio. Also could keep connection points.
- Automatic layout (automatically layout the diagram based on certain rules)
- Fit diagram border: allow to fit the diagram border
  
## Rich text editor [partially done]

- See: https://github.com/modeldriven-hu/astah-rich-document

For documenting model elements Astah only provides a text area. In this plugin, when the user select a model element, the
associated documentation would be visible in the rich text editor. When the user deselects a model element, then it the 
editor will be empty and disabled. When user selects multiple elements, the editor will be likewise empty and disabled.
Functions:
- bold
- italic
- align (left, right, center, justify)
- color (background, foreground)
- list
- numbering
- table
- link
- image?
- undo/redo support
- etc.

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
- List plugins
- Search for plugin
- Filter plugins by type
- Notify user when a new version of an installed plugin is available
- Check digital signature before install
- etc.

## OpenAPI import

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

## Statistics

Display statistics of the model. Number of model elements, by type, number of diagrams, by type, etc.

## OSLC support

This is a challenging but super interesting task. Add OSLC client support to Astah so that a connection to an OSLC server could
be built up. A good starting point could be an integration to requirements part of the following reference implementation:  
https://github.com/oslc-op/refimpl

## Model import without Astah

Being able to offline import a model and run for example validation rules on it. It would be great if we could put a model in a
CI/CD environment and have a git hook to run verification / model transformation.

## HTML generation

Export a document into a HTML.

## Model server

A model server could get a model file and serve it to various interfaces. OSLC, REST, etc. It could also support locking/version
management.

