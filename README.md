# javascript

algorithms

Binary search:
let arr = [1, 2, 3, 4, 5, 6, 7, 8];
let start = 0;
let end = arr.length - 1;
let target = 0.5;

function binarySearch(arr, start, end, target) {
	let mid = Math.floor((start + end) / 2);
	if (start > end) return false;
	if (arr[mid]===target) return true;
	if (arr[mid] > target) return binarySearch(arr, start, mid - 1, target);
	if (arr[mid] < target) return binarySearch(arr, mid+1, end, target);

}
console.log(binarySearch(arr, start, end, target));
