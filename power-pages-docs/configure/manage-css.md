---
title: Manage CSS files in Power Pages
description: Learn how to upload CSS files in the design studio
author: ankitavish
ms.topic: conceptual
ms.custom: 
ms.date: 09/20/2022
ms.subservice:
ms.author: avishwakarma
ms.reviewer: ndoelman
contributors:
    - ankitavish
    - nickdoelman
    - ProfessorKendrick
---

# Manage CSS files

Cascading Style Sheets (CSS) allows you to control the formatting and styling of your site. 

By default, new Power Pages sites will have *bootstrap.min.css*, *theme.css* and *portalbasictheme.css* files installed as part of the site templates. 

You can modify the style using the [Styling workspace](../getting-started/style-site.md) or you can upload your own custom CSS files. 

When you upload a new custom CSS file, it will be available as a web file in the [Portal Management app](portal-management-app.md).

> [!NOTE]
> Power Pages sites use Bootstrap 3.3.x. Site developers should not replace Bootstrap 3 with other CSS libraries as some of the scenarios in Power Pages are dependent on Bootstrap 3.3.x. For more information, see [Understanding Bootstrap framework](#understanding-bootstrap-framework) and [Customize Bootstrap](#customize-bootstrap) sections in this article.

## Manage custom CSS files in the Styling workspace

1. Go to [Power Pages](https://make.powerpages.microsoft.com/).

1. Select **Edit** on the site you want to add a page.

1. Select the **Styling** workspace.

1. Select the **Manage CSS** option under more options in Styling Workspace. 

    :::image type="content" source="media/manage-css/manage-css.png" alt-text="Manage CSS files using design studio.":::

## Upload CSS files

In the **Manage CSS** panel you'll see a list of the default CSS files:

- bootstrapmin.css
- theme.css
- portalbasictheme.css

To upload your custom CSS file, select **Upload** and choose your custom CSS file.

:::image type="content" source="media/manage-css/upload-css.png" alt-text="Upload CSS files using design studio.":::

> [!NOTE]
> - You can upload custom CSS files of a size up to 1 MB.
> - Once the custom CSS file is uploaded the preview will reflect on right side.
> - The uploaded custom CSS files will be applicable for all themes.

## More options

Select the **...** (ellipse) to right of the custom CSS file, where you can move the file higher or lower in precedence and disable the custom CSS file.

> [!NOTE]
> CSS files listed at bottom take higher precedence, meaning that if two files contain an update the same property, the update contained in the file lower in the list will be applied.

:::image type="content" source="media/manage-css/css-order.png" alt-text="Order of precedence for CSS files.":::

## Architecture

Any custom CSS file is at lower priority than the default *portalbasictheme.css* and higher than *theme.css*. This prioritization is to encourage customizing styles using style panel for out of box styling options.

> [!NOTE]
> We recommend custom CSS should be used to format only styles which aren't provided out of box in style pane.

> [!WARNING]
> Do not deactivate, delete or change the display order of any of the default CSS files (bootstrap.min.css, theme.css, or portalbasictheme.css). You will see an error in the design studio.</br>
> :::image type="content" source="media/manage-css/update-css-pma.png" alt-text="Update CSS files using the Portals Management app."::: </br>
> Open the **Portal management app** and to restore the default state and display order of the default CSS files to resolve the issue.

### Delete a custom CSS file

1. The CSS files are stored as [web files](advanced-config.md#web-files). To remove the custom CSS file, go to the [Portal Management app](portal-management-app.md) and select **Web Files**. 

1. Locate the custom CSS file record. You may need to filter on the **Name** and **Website** values to locate the correct record.

1. Once the web file record is selected, select **Delete**.

1. In the design studio, select **Sync configuration** to clear the styling changes from the custom CSS.

## Understanding Bootstrap framework

Bootstrap is a front-end framework that includes CSS and JavaScript components for common web application interface elements. It includes styles for [navigation elements](https://getbootstrap.com/components/#nav), [forms](https://getbootstrap.com/css/#forms), [buttons](https://getbootstrap.com/css/#buttons), and a [responsive grid layout system](https://getbootstrap.com/css/#grid) that allows site layouts to dynamically adjust to devices that have different screen sizes, such as phones and tablets. By using the Bootstrap layout system, you can develop a single site that presents an appropriate interface to all devices your customers might use.

The templates included with Power Pages are implemented by using standard Bootstrap components with minimal additional custom styles. So when you implement the templates, you can take advantage of Bootstrap customization options. You can quickly customize the theme (fonts, colors, and so on) in a way that's applied consistently across the site.

### Customize Bootstrap

Bootstrap supports customization through a set of variables. You can set any or all of these variables to custom values and then download a custom version of Bootstrap that is compiled based on these values.

The power of Bootstrap variables is that they don't dictate the style of a single element. All styles in the framework are based on and derived from these values. For example, consider the variable `@font-size-base`. This specifies the size that Bootstrap assigns to normal body text. However, Bootstrap also uses this variable to indicate the font size for headings and other elements. The size for an H1 element might be defined as 300 percent of the size of `@font-size-base`. By setting this one variable, you control the entire typographic scale of your portal in a consistent way. Similarly, the `@link-color` variable controls the color of hyperlinks. For the color you assign to this value, Bootstrap will define the hover color for links as 15 percent darker than your custom value.

The standard way to create a custom version of Bootstrap is [through the official Bootstrap site](https://getbootstrap.com/customize/#less-variables). However, due to the popularity of Bootstrap, many third-party sites have also been created for this purpose. These sites might provide an easier-to-use interface for Bootstrap customization or predesigned versions of Bootstrap for you to download. [The official Bootstrap customizer](https://getbootstrap.com/customize/) site has more information about Bootstrap customization.  

When you download a customized version of Bootstrap, it contains the following directory structure.

```
css/
    |-- bootstrap.min.css 
img/
    |-- glyphicons-halflings-white.png 
    |-- glyphicons-halflings.png 
js/ 
    |-- bootstrap.min.js
```

Or, depending on the customizer application used, it might only contain bootstrap.min.css. Regardless, bootstrap.min.css is the file that contains your customizations. The other files are the same for all custom versions of Bootstrap and are already included in your portal.

### See also

- [Microsoft Training: Advanced CSS in Power Apps portals](/learn/modules/extend-power-app-portals/4-portal-css)
- [Microsoft Training: Advanced client-side development](/learn/modules/extend-power-app-portals/5-advanced-portal-development)
