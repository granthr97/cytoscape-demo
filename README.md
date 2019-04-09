- Clone this repo
- Create an index.html file with

```
<!doctype html>
<html>
<head>
    <title>Tutorial 1: Getting Started</title>
    <script src='cytoscape.js'></script>
</head>
<body></body>
</html>
```

- Create a graph

```
<body>
...
    <div id="cy"></div>
...
</body>
```

- Add the following styles

```
<head>
...
<style>
  #cy {
      width: 100%;
      height: 100%;
      position: absolute;
      top: 0px;
      left: 0px;
  }
</style>
...
</head>
```

- Create a cytoscape graph instance

```
<body
...
var cy = cytoscape({
  container: document.getElementById('cy'),
  elements: [
    { data: { id: 'a' } },
    { data: { id: 'b' } },
    {
      data: {
        id: 'ab',
        source: 'a',
        target: 'b'
      }
    }]
});
...
</body>
```

- The final index.html file should look like this

```
<!doctype html>

<html>

<head>
    <title>Tutorial 1: Getting Started</title>
    <script src="cytoscape.js"></script>
</head>

<style>
    #cy {
        width: 100%;
        height: 100%;
        position: absolute;
        top: 0px;
        left: 0px;
    }
</style>

<body>
    <div id="cy"></div>
    <script>
      var cy = cytoscape({
        container: document.getElementById('cy'),
        elements: [
          { data: { id: 'a' } },
          { data: { id: 'b' } },
          {
            data: {
              id: 'ab',
              source: 'a',
              target: 'b'
            }
          }]
      });
    </script>
</body>
</html>
```
