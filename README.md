# Cadence Utility Functions
A collection of utility functions in Cadence


## Square Root

```cadence

/** Square Root using the Babylonian Method **/
pub fun sqrt(_ num: UFix64) : UFix64 {
  var a: UFix64 = num;
  var b: UFix64 = 1.0;

  // Set the precision (e.g. 0.00001) - the higher it is, the slower the execution.
  while ((a - b) > 0.00001) {
    a = (a + b) / 2.0;
    b = num / a;
  }
  // Return the calculated square root
  return a;
}

```

**Usage:** [Playground](https://play.onflow.org/200636eb-c3d7-4752-af69-48a6cfcd2a64?type=script&id=a4d910b3-fbf1-413d-9aef-891502ef43e3)

Alternative implementation by @bluesign

```cadence
pub fun sqrt(_ x: Fix64) : Fix64 {
  var r = x
  while (r - x/r > 0.0000001 ){
    r = ( r +  x/r ) / 2.0  
  }
  return r
}
```
