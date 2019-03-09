# ts-pq

A Typescript priority queue for grid node values

## How to use

```javascript
const pq = new PriorityQueue();

pq.insert({ x: 0, y: 1 }, 2);
pq.insert({ x: 2, y: 1 }, 10);
pq.insert({ x: 5, y: 0 }, 0);

pq.values(); // [{ x: 5, y: 0 }, { x: 0, y: 1 }, { x: 2, y: 1 }]
pq.pop(); // { x: 5, y: 0 }
pq.shift(); // { x: 2, y: 1 }
```

## Documentation

### Methods

- insert

  - type: (val: T, priority: number) => [T, number][]
  - perf: O(n) time complexity insertion
  - description: Merge sort a new value in the queue

- has

  - type: ({ x, y }: T) => boolean
  - perf: O(n) time complexity
  - description: Check if node is in the queue

- get

  - type: ({ x, y }: T) => T | undefined
  - perf: O(n) time complexity
  - description: return node from the queue depending on x / y parameter

- shift

  - type: (priority: boolean) => T | [T, number] | undefined
  - perf: O(1) time complexity
  - description: return node with highest weight, include priority weight or not

- pop

  - type: (priority: boolean) => T | [T, number] | undefined
  - perf: O(1) time complexity
  - description: return node with lowest weight, include priority weight or not

- priorities

  - type: () => number[]
  - perf: O(n) time complexity
  - description: Return the sorted priorities of the queue

- values

  - type: () => T[]
  - perf: O(n) time complexity
  - description: Return the sorted nodes of the queue

- size

  - type: () => number
  - perf: O(1) time complexity
  - description: Return the length of the queue

- toArray

  - type: (values: boolean) => [T, number][] | T[]
  - perf: O(1) | O(n) time complexity
  - description: Return the array used as heap as array of tuples or array of nodes
