# javascript

// Algorithms:

// Binary search:

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

// Merge Sort:

function mergeSort(arr) {
	if (arr.length < 2) {
		return arr;
	}
	
	const middleIndex = Math.floor(arr.length/2);
	const leftArr = arr.slice(0, middleIndex);
	const rightArr = arr.slice(middleIndex, arr.length);
	
	return merge(mergeSort(leftArr), mergeSort(rightArr));
}

function merge(leftArr, rightArr) {
	let resultArr = [];
	let leftIndex = 0;
	let rightIndex = 0;	
	
	while (leftIndex < leftArr.length && rightIndex < rightArr.length) {
		if (leftArr[leftIndex] < rightArr[rightIndex]) {
			resultArr.push(leftArr[leftIndex]);
			leftIndex += 1;
		} else {
			resultArr.push(rightArr[rightIndex]);
			rightIndex += 1;
		}
		
	}
	
	return resultArr.concat(leftArr.slice(leftIndex)).concat(rightArr.slice(rightIndex));
}

let array = [5, 2, 9, 6, 0, 7, 3];
console.log(mergeSort(array));

// Pattern:
// Static sliding window:
function main() {
	const k = 5;
	let nums = [2, 11, -3, 9, -8, 25, 1, 13, 8, -16];
	
	var answer = findMax(nums, k);
	var maxAverage = answer / k;
	console.log(maxAverage);
}

function findMax(nums, k) {
   var windowSum = 0;
	var start = 0;
	var end = 0;
	var maxi = -1*10**4;
	var n = nums.length;
	
	for(end = 0; end < n; end++) {
		windowSum += nums[end];
		if ((end - start + 1) == k) {
			maxi = Math.max(maxi, windowSum);
			windowSum -= nums[start];
			start += 1;
		}
	}
	return maxi;
}
main();
