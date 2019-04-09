# Basic Demo Tutorial

- Clone this repo
- Create an index.html file with

```
<!doctype html>
<html>
<head>
    <title>Tutorial 1: Getting Started</title>
    <script src='cytoscape.min.js'></script>
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
    <script src="cytoscape.min.js"></script>
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

# Non-basic Tutorial

- Do all the following on top of the basic above
- Create a complete graph of elements

```
var nodes = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j"];
var elements = [];
for (var i = 0; i < nodes.length; i++) {
  elements.push({ data: { id: nodes[i] } });
}
for (var i = 0; i < nodes.length; i++) {
  for (var j = 0; j < nodes.length; j++) {
    if (i != j) {
      elements.push({
        data: {
          id: nodes[i] + nodes[j],
          source: nodes[i],
          target: nodes[j]
        }
      });
    }
  }
}
```

- Replace the elements

```
...
elements: elements,
...
```

- Change the layout

```
...
cy.layout({
    name: 'circle'
}).run();
```
