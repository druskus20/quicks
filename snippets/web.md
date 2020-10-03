# Web Design snippets
#### After element selector
This is a very niche CSS selector, its basic intent is to select an element after another. The notation is the following:
```scss
element + element 
```

However, I found this might be useful for removing margins or padding on certain elements.
```scss
// this is a very handy addition to the common way of CSS "normalization": 
* {
  margin: 0;
} 

// By adding the following CSS rule we can set margins for every element that's not the first (usually container headings),
//  instead of just removing margins completely.
* + * {
  margin: 10px 0 0 0;
}
```

