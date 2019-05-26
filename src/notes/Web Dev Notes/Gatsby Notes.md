# Gatsby Notes

### About Gatsby

Gatsby is a static site generator that uses React "under the hood"

Gatsby data sources can be CMSs, Markdown, and Data (APIs, DBs, JSON, etc.)

The process of Gatsby is the Data Source -> GraphQL -> HTML\CSS\React -> Deploy

**<u>Steps to get Gatsby ready</u>**

1. Install Gatsby CLI, type `npm install --global gatsby-cli`
2. Create new Gatsby app with  `gatsby new <name of project>`
3. Go to app folder
4. Type `gatsby develop` to get the application running
5. Imported needed plugins
6. Add plugins to `gatsby-config`
7. Change title of application 
8. Create template(s)
9. Enter all of the needed code in the `gatsby-node.js` file



A new Gatsby application can be built using one of the many Gatsby premade demos

The syntax to create a Gatsby app with one of the premade demos is `gatsby new <name of app> <url of gatsby premade demo>`

* Instead of typing out the whole URL,  `https://github.com/datocms/snipcart-gatsby-demo.git` all that would need to be typed would be `datocms/snipcart-gatsby-demo`

 

### Gatsby Plugins

When using a Gatsby plugin, these need to be added to the `plugins` section of `gatsby-config.js`

The `gatsby-plugin-sass` allows Gatsby to use Sass to style the website instead of styling using styled components

Source plugins are used to allow another type of source that Gatsby can use

The `gatsby-source-filesystem` allows file to used within Gatsby, which is treated like an external API

When adding a source plugin like `gatsby-source-filesystem` to `gatsby-config.js` there is more information than just the name of the plugin that needs to be entered. What needs to be entered is below:

```js
{
    // The name of the plugin
      resolve: 'gatsby-source-filesystem',
      options: {
        // The location of where the files will be
        path: `${___dirname}/src/posts`,
        name: "posts",
      }
    }
```

Transformer plugins are needed to convert data that is not accessible by default. After this data is converted, Gatsby can then query against that data using GraphQL.

The transformer plugin that is needed to use markdown files is `gatsby-transformer-remark`

### Markdown Files

All markdown files that will be used as a page or blog post need to have the front matter as the first lines of the document. An example of how this should look is:

```markdown
---
path: "/first-post"
title: "First Blog Post"
---
```

And then after the front matter the rest of the document can be treated like a normal markdown file.

The information that is inside of the front matter can be whatever you need to pass into the template.

The template for a post would look like the code below:

``` jsx
import React from "react";
import Helmet from "react-helmet";

export default function Template({data}) {
    const {markdownRemark: post} = data;
    
    return (
        <div>
            <h1>{post.frontmatter.title}</h1>
        </div>
    )
}
```

`post.frontmatter.title` points to the `title` key that is in the front matter of the post markdown files

The other part of the template is the graphQL query that will find the file for the post that is being requested. An example of this section looks like the code below:

```
export const postQuery = graphql`
    // Runs the query where the path of the post is passed in as a string
    query BlogPostByPath($path: String!) {
        // Returns the post that has the path that is the path that was passed in
        markdownRemark(frontmatter: {path: { eq: $path}}) {
            // This is all of the data from the markdown file that should be returned
            html
            frontmatter {
                path
                title
            }
        }
    }
`
```



Inside of the `allMarkdownRemark( )`  function is where parameters would be passed for sorting and limiting if they are needed. If there is no need to do any sorting or limiting then the parenthesis can be omitted.

In order for the pages to show up on the site, they need to be found by Gatsby. This is done within the `gatsby-node.js` file. An example of what this file would look like is shown below:

``` jsx
onst path = require("path");

 exports.createPages = ({boundActionCreators, graphql}) => {
     const {createPage} = boundActionCreators;

     // This points to where the template fill is
     const postTemplate = path.resolve("src/templates/post.js");

     // This query searches for all of the blog posts and creates a page for them
     return graphql(`{ 
        allMarkdownRemark {
          edges {
              node {
                  html
                  id
                  frontmatter {
                    path
                    title  
                  }
              }
          }  
         }
     }`)
     .then(res => {
         if(res.errors) {
             return Promise.reject(res.errors);
         }

         res.data.allMarkdownRemark.edges.forEach( ({node}) => {
            createPage({
                path: node.frontmatter.path,
            component: postTemplate
            })
         })
     })
 }
```

#### Deploying

When all of the changes that are needed are complete, the command `gatsby build` should be ran. When the site is built, there will be a folder named `public` that would need to be uploaded to the website hosting provider. After this is done, the newly created Gatsby site should work.