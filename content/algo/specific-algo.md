---
title: First Week
description: First Programming Week
slug: w1
img: blog-2.jpg
---
# Day One

## River Sizes
![](img/2022-04-10-19-29-15.png)

```javascript
        function riverSizes(matrix) {

            const sizes = [];
            // Create an all visited map.
            const visited = matrix.map(row => row.map(value => false));
            for (let i = 0; i < matrix.length; i++) {
                for (let j = 0; j < matrix[i].length; j++) {
                    if (visited[i][j]) continue;
                    traverseNode(i, j, matrix, visited, sizes);
                }
            }
            return sizes.length;
        }

        function traverseNode(i, j, matrix, visited, sizes) {
            let currentRiverSize = 0;
            const nodesToExplore = [
                [i, j]
            ];
            while (nodesToExplore.length) {
                const currentNode = nodesToExplore.pop();
                i = currentNode[0];
                j = currentNode[1];

                if (visited[i][j]) continue;
                visited[i][j] = true;
                if (matrix[i][j] == 1) continue;
                currentRiverSize++;
                const unvisitedNeighbors = getUnvisitedNeighbors(i, j, matrix, visited);
                for (const neighbord of unvisitedNeighbors) {
                    nodesToExplore.push(neighbord);
                }
            }
            if (currentRiverSize > 0) sizes.push(currentRiverSize);
        }

        function getUnvisitedNeighbors(i, j, matrix, visited) {
            const unvisitedNeighbors = [];
            if (i > 0 && !visited[i - 1][j]) unvisitedNeighbors.push([i - 1, j]);
            if (i < matrix.length - 1 && !visited[i + 1][j]) unvisitedNeighbors.push([i + 1, j]);
            if (j > 0 && !visited[i][j - 1]) unvisitedNeighbors.push([i, j - 1]);
            if (j < matrix[0].length - 1 && !visited[i][j + 1]) unvisitedNeighbors.push([i, j + 1]);
            return unvisitedNeighbors;
        }
```

# Day Two 

# Day Three

# Day Four


# Day Six

# Day Seven


