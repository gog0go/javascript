# javascript

algorithms

Binary search:
let arr = [];
let start = 0;

let target = 478;
for (let i = 1; i <= 2048; i++) {
	arr.push(i);
}

let end = arr.length - 1;
function binarySearch(arr, start, end, target) {
	console.log(arr.slice(start, end));
	if (start > end) return false;
	let mid = Math.floor((start + end) / 2);
	if (arr[mid]===target) return true;
	if (arr[mid] > target) return binarySearch(arr, start, mid - 1, target);
	else return binarySearch(arr, mid+1, end, target);

}
console.log(binarySearch(arr, start, end, target));
