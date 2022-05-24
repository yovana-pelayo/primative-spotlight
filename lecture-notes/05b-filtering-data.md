# Filtering Data

Previously, we used an `id` to uniquely identify each object in our array of data. Since each id is unique, we can use that id to filter our data when we want to find a specific object.

```js
export function findById(id, data) {
  return data.find((item) => item.id === id);
}
```

This allows us to use the list/detail pattern.

    - list pages display a list where each item contains a link to a detail page about that particular item
    - detail pages shows that item's id in the url. Detail page shows info about just that item

```js
// get the id from URL: www.cool-cats.com/detail/?id=4
const params = new URLSearchParams(window.location.search);
const id = params.get("id");

// use the id to fetch the dog
const cat = findById(id, cats);

// render the cat detail
const catDetailEl = renderCatDetail(cat);
catDetailContainer.append(catDetailEl);
```
