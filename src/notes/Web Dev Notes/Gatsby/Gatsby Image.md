```jsx
<StaticQuery query ={graphql`
...query goes here...
`} render={(data) => {
... JSX for page goes here ...
}}
```

```jsx
name: file(relativePath: {eq: "nameofpic.png"}) {
childImageSharp {
fluid(maxWidth:1600) {
...GatsbyImageSharpFluid
}
}
}
```

