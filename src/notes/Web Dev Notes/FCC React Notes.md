## FCC React Notes

To make a comment in JSX the comment would need to be wrapped in the following code `{/* */}`

Self closing HTML elements like `<hr>` and `<br>` need to be typed like `<hr />` and `<br />` while using JSX. All HTML tags can be closed in the same way but doing things this way there is no way to put any data inside of the tag 

```jsx
class TypesOfFood extends React.Component {
  constructor(props) {
    super(props);
  }
  render() {
    return (
      <div>
        <h1>Types of Food:</h1>
        {/* change code below this line */}
 
        {/* change code above this line */}
      </div>
    );
  }
};
```

