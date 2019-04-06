---
layout: docs
---

# Neatline Editor: An Overview

## At a glance

- The Neatline editor is the interactive application that allows users to build the content of their Neatline exhibit.
- The [**Records**](#records) tab within the editor is where you create and search for Neatline records, the content of your exhibit.
- The [**Styles**](#styles) tab is where you can set an exhibit's default focus and zoom and use the Neatline stylesheet.
- The [**Plugins**](#plugins) tab allows you to access settings for the enabled Neatline widgets in the exhibit.

## Editor Overview

The Neatline editor is the interface where you build the content of your exhibit. Access the editing enviroment by clicking on the exhibit [title](/docs/managing-exhibits) in the "Browse Exhibits" view. The left panel within the editor includes tabs for **Records**, **Styles**, and **Plugins**. If there are no plugins (/docs/widgets) [enabled](/docs/creating-exhibits#widgets) for the exhibit, the **Plugins** tab will not be displayed. 

![Screenshot of Neatline editing environment](/assets/images/docs/editor-overview.png)

On opening the exhibit editor, your selected [**Default Spatial Layer**](/docs/creating-exhibits#default-spatial-layer) will appear. For map layers, the default location is set at the coordinates 0° N, 0° E (/docs/to change your exhibit's default location, see [here](/docs/exhibit-styles-tab#default-map-focus).)

To view the [**Enabled Spatial Layers**](/docs/creating-exhibits#enabled-spatial-layers) in your exhibit, click on the layers icon on the right side of the page, and select a layer option to change the visible map base layer:

![Screenshot layers icon](/assets/images/docs/layers-icon.png)   ![Screenshot layers icon selected](/assets/images/docs/layers-icon-open.png)

**Note:** The [Default Spatial Layer](/docs/creating-exhibits#default-spatial-layer) and [Enabled Spatial Layers](/docs/creating-exhibits#enabled-spatial-layers) can only be set in the [Exhibit Settings](/docs/creating-exhibits#exhibit-settings). 

## Records

![Screenshot of Records tab](/assets/images/docs/records-tab.png)

Select the **Records** tab to create, search and edit the Neatline records in your exhibit. **Records** are the primary content of the Neatline exhibit, including any vector annotations, timeline and waypoint context, WMS overlay layers, and text annotations in the exhibit narrative. 

For more on **Records**, see the related documentation: [Records Overview](/docs/records-overview), [Creating New Records](/docs/creating-records), [Importing Omeka Items](/docs/importing-omeka-items), [Searching Records](/docs/searching-records)

## Styles

![Screenshot of Styles tab selected](/assets/images/docs/styles-tab.png)

Select the **Styles** tab to edit higher-level settings for your exhibit. This section includes the following settings:

- The [Neatline Stylesheet](/docs/neatline-stylesheets), a code editor that uses a simplified, Neatline-inflected dialect of CSS to perform bulk updates on large groups of related records clustered together by tags (/docs/see [Editing Record Groups](/docs/style-tab-groups) for more information about tags).
- [Default Map Focus and Zoom](/docs/exhibit-styles-tab#default-map-focus) 
- [Restricted Map Extent](/docs/exhibit-styles-tab#restricted-map-extent)
- [Minimum Map Zoom](/docs/exhibit-styles-tab#minimum-map-zoom)
- [Maximum Map Zoom](/docs/exhibit-styles-tab#maximum-map-zoom)

For details on these settings, see [Exhibit Styles Tab](/docs/exhibit-styles-tab) and [Using Neatline Stylesheets](/docs/neatline-stylesheets).

## Plugins

![Screenshot of plugins tab selected](/assets/images/docs/editor-plugins-tab.png)

Select the **Plugins** tab to display a drop-down list of the [enabled widgets](/docs/creating-exhibits#widgets) in your exhibit. Select a widget name to edit it's higher-level settings. If this tab is not visible, there are no widgets enabled in your exhibit.

For details on these settings, see documentation on Neatline plugins: [SIMILE Timeline](/docs/working-with-the-simile-timeline-widget), [Waypoints](/docs/working-with-the-waypoints-plugin)
