# sort-function-TDD
sort function TDD HYF class source code

```js
/* expects ray to be an Array, returns an Array that is sorted, shouldnt mutate the original array, and should return null on invalid parameter values */
function sort(ray){
	if(!Array.isArray(ray)){
  	console.error('Called sort with non-array');
    return null;
  }
	if(ray.length === 0) return ray;
  const sorted = ray.slice(0);
  var swapped;
  do {
      swapped = false;
      for (var i=0; i < sorted.length-1; i++) {
          if (sorted[i] > sorted[i+1]) {
              var temp = sorted[i];
              sorted[i] = sorted[i+1];
              sorted[i+1] = temp;
              swapped = true;
          }
      }
  } while (swapped);
  
  return sorted;
}

// Tests

function test1(){
	var s = sort([]);
	if(Array.isArray(s) && s.length === 0){
  	console.log('Success test 1, is an empty array');
  }
  else {
  	console.error('Failed test 1');
  }
}

function test2(){
	var s = sort(3);
  if(s === null){
  	console.log('Success test 2, return null if passed a number');
  }
  else {
  	console.error('Failed test 2', s);
  }
}

function test3(){
	var sorted = sort([2,1]); // expect [1,2]
  if(sorted[0] === 1 && sorted[1] === 2){
  	console.log('Success test 3, sorts array with two values');
  }
  else {
  	console.error('Failed test 3', sorted);
  }
}

function test4(){
	var initial = [2,1];
	var sorted = sort(initial);
  if(initial[0] === 2 && initial[1] === 1){
  	console.log('Success test 4, doesn\'t mutate array');
  }
  else {
  	console.error('Failed test 4, mutates array');
  }
}

// Run Tests

test1();
test2();
test3();
test4();

```
