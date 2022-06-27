# How to Extract URL Search Parameters

Assume you have a url to looks like this `https://myshop.com/products?id=1`

## How can I grab that `id` value?

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bjvbeb4ar60szqymbu6j.gif)

Well today, we are going to see how can grab the id from the url using vanilla JavaScript.

## Main Concept

### Window.location

> `location` is is a window property that contains information about the current Document. Document referes to the page that is being rendered.

### URLSearchParams API

Accoding to MDN:

> The URLSearchParams API defines utility methods that can be used to manipulate the URL string like ours here: `"https://myshop.com/products?id=1"`

## How to Use `URLSearchParams` and `location` to achieve this?

Just before we step on our fuel pedal and speed up using the URLSearchParams API, we need to elaborate on one more thing, `window.location`

Oh yeah! when invoked, the `window.location` returns an object with all the information regarding the current Document. For example, if I run `window.location` in the console of the this window I am working on right now, this is what I get:

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/su09af1c0w9jwnqd8nqt.png)

As you can see, there is plenty of information right there 👆👆

With this knowlege of the `window.location` property, we are just one property away from getting the parameters from our link `https://myshop.com/products?id=1`

Let me expand the previous object so that you can see how close we are:
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fk4hz822k4tyefau7jrt.png)
You see what I mean? Yeah! Right there you can see the `search: ""`. And yeah, in this case it is empty because  
 there there are no query parameters in the current window.

If our link looked like this `https://myshop.com/products?id=1`, then `search` will look like this:
`search: "?id=1"`

## Let us nail it

In order to get the search parameter, we shall combine `URLSearchParams` and `window.location.search` like this:

```js
let searchParams = new URLSearchParams(window.location.search);
```

In the snipet above, `new URLSearchParams(window.location.search)` will split the url query (id=1) into key/value pairs.

Therefore, the variable `searchParams` will look like this:

```js
searchParams = {
  id: 1,
};
```

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/xcayo3td1axeevyyyfip.gif)
Oh yeah! We got it, right? From here, all we need to do is access `id` and it will give us the value, `1` in this case.

This is how you do it:

```js
let id = searchParams.get("id");
console.log(id);
//=> 1
```

## Key Takeaways

- `window.location` is a proerty that returns all the information regarding the current Document.

- `URLSearchParams API` allows us to manipuate urls.

- `window.location.search` returns the `search` property which contains the list of our url queries.
- Together, `URLSearchParams API` and `window.location.search` can help us extract search parameters from a url.
- We can get key/value pairs of the query parameters by passing the url to the `URLSearchParams API` like this: `new URLSearchParams("url")`.

## How do you go about extracting URL search parameters? Kindly share in the comments below
