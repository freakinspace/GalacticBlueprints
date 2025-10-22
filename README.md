# GalacticBlueprints

A list of json datasets about pirate galaxy items.
<br>These include information about items (their power, prices, drop information...), spaceships, and a few other utility datasets.

## Technical documentation

These datasets are fully data driven and do not include behavioral information. It is left to the user to understand what the attributes means and how they interact with the game engine.
For example, aim computer entries have an "accuracy" attribute, you need to know that this is an additive percentage, and what to add it with to compute your chance to hit.

Every dataset is a valid json object with the following format:

```json
{
    "dataset": "datasetName",
    "data": ...
}
```

The data attribute may be an object or an array, depending on the need of the specific dataset. Only the json root is guarenteed to be an object.
To parse and use a dataset, one may use the following javascript snippet:

```javascript
import myDatasetName from './datasetName.json' assert { type: 'json' };

// Content of your javascript file...
console.log(myDatasetName);
```

## Using in your project

This repository only contains data, and may be used in your own repository.
To do so, it is recommended to import all datasets using a ``git submodule``.

Here is a list of git commands to do so, assuming your working directory is currently the root of your project:

```bash
git submodule add https://github.com/freakinspace/GalacticBlueprints
git submodule update --init --recursive
```

And to fetch new data from the repository head if your local submodule becomes outdated:

```bash
cd .\GalacticBlueprints\
git fetch
git checkout main
cd ..
```
