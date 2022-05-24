# Supabase Code Snippets

## Supabase Client

### Fetching All Columns

```js
const { data, error } = await client.from("dogs").select("*");
```

### Fetching Related Data

In this example, each player belongs to a team

```js
const { data, error } = await client.from("teams").select("*, players(*)");
```

### Matching a specific ID

```js
const { data, error } = await client.from("dogs").select("*").match({ id: 1 });
```

OR

```js
const { data, error } = await client.from("dogs").select("*").eq("id", 1);
```

### Creating a new row

Remember that Supabase will create the ID for you

```js
const dog = {
  name: "Benny",
  age: 6,
  breed: "Terrier",
  image: "https://placedog.net/1000/563?id=110",
  bio: "Best pup ever",
};
const { data, error } = await client.from("dogs").insert(dog);
```

### Updating a row

`.update()` accepts an object with the key / value pairs you want to update

```js
const { data, error } = await client
  .from("dogs")
  .update({ name: "Ben Donich" })
  .match({ id: 1 });
```

### .single

Adding `.single()` to any queries that return a single row (matching by ID, creating, updating) will return the data as an object instead of an object nested inside an array
