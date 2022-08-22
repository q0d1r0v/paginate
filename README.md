# paginate-by-oybek

## parameters

```
page => number

length => number

updatePage => method

```

## for example

```
<paginate :page="1" :length="27" @updatePage="goServer" />

methods: {
    goServer(pageNumber) {
      console.log(pageNumber)
    }
}

```

## first step =>
```
npm install
```

### next step => 
```
npm run dev
```

