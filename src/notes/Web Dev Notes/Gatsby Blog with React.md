# Gatsby Blog with React

#### Setting up Gatsby 

To install the Gatsby CLI type `npm install -g gatsby-cli` 

After the Gatsby CLI is done installing type `gatsby new <name of blog>`

Change into the newly created folder

To start up a development website, run the command `gatsby develop`

After the development site is running, the development website is available at http:\\localhost:8000

#### File Structure

The `.cache` folder is a folder that doesn't need to be messed with.

As usual, the `node_modules` folder is where all of the node files are stored.

The `public` folder is where the static site will be created into.

The `src` folder is where all of the files that will be modified are located.

	Inside of the `src` folder, there are 3 sub-folders; components, layouts, and pages.

	The `components` folder has all of the components that are used in the website.

	The `layouts` folder has the CSS file for the site and the layouts for all of the pages 		that need to have a specific layout.

	The `pages` folder has all of the pages that are used on the site.

The `gatsby-config.js` file is where the title of the site and the plugins that are used are listed.

#### Making Changes to the site

When adding a new page to the site, the name of the function for the page has to be the same as the name for the export default. An example of this is below:

``` jsx
import React from 'react'
import Link from 'gatsby-link'

const SecondPage = () => (

  <div>
    <h1>Hi from the second page</h1>
    <p>Welcome to page 2</p>
    <Link to="/">Go back to the homepage</Link>
  </div>
)

export default SecondPage
```

Within the JSX portions of the code, a normal anchor tag cannot be used. In it's place a Link tag is used. The syntax that is used for a Link tag is `<Link to="/">Go back to the homepage</Link>`

##### Gatsby Plugins

The list of plugins that are available to be used with Gatsby can be found at https://www.gatsbyjs.org/plugins/

To install a plugin run the command `npm install --save <name of plugin>`

After the plugin is installed, the plugin needs to be added to the `gatsby-config.js` file under the plugins section.

* Some of the plugins have to have more information entered into the config file. To find out if this is the case for a specific plugin is to look at the plugin page on the Gatsby website.







Left off at 2:22 of https://www.youtube.com/watch?v=n1NaVkKdrwc&index=4&list=PLLnpHn493BHHfoINKLELxDch3uJlSapxg