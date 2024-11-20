#MachineLearning 
#### By: Coursera - Mathematics for Machine Learning 
---
When working with complex functions,


```graph
bounds: [-8,4,8,-4]
elements: [
	{type: slider, def: [[1,3],[5,3],[1,10,200]], att: {name: "n"}},
	{type: slider, def: [[1,2],[5,2],[-10,-3,0]], att: {name: "start"}},
	{type: slider, def: [[1,1],[5,1],[1,6,10]], att: {name: "end"}},
	{type: functiongraph, def: ["f:Math.sin(x)+Math.cos(x)", "f:e1", "f:e2"]},
	{type: riemannsum, def: ["f:Math.sin(x)+Math.cos(x)","f:e0", "left", "f:e1", "f:e2"], att: {fillColor: "#ffff00", fillOpacity: 0.3}},
	{type: text, def: [-4, 2, "'Sum = ' + f:e4.toFixed(4)"], att: {fillColor: "#ffff00", fillOpacity: 0.3}},
]

```


```graph
bounds: [-10, 10, 10, -10]
bounds3d: [[-5,5],[-5,5],[-5,5]]
axis: false
keepAspectRatio: true
elements: [
	{type: circle3d, def: [[1,1,1], [1,1,1], 3]}
]
```

