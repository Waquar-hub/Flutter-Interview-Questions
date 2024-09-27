# Flutter-Interview-Questions
Here are some logical questions on lists that you can solve using Dart, similar to reversing a list. Each question also has a sample solution.

1. Find the sum of all elements in the list
dart
Copy code
int sumOfList(List<int> list) {
  int sum = 0;
  for (int i = 0; i < list.length; i++) {
    sum += list[i];
  }
  return sum;
}

void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  print(sumOfList(numbers)); // 15
}
2. Find the maximum element in the list
dart
Copy code
int findMax(List<int> list) {
  int max = list[0];
  for (int i = 1; i < list.length; i++) {
    if (list[i] > max) {
      max = list[i];
    }
  }
  return max;
}

void main() {
  List<int> numbers = [1, 8, 3, 4, 9];
  print(findMax(numbers)); // 9
}
3. Find the minimum element in the list
dart
Copy code
int findMin(List<int> list) {
  int min = list[0];
  for (int i = 1; i < list.length; i++) {
    if (list[i] < min) {
      min = list[i];
    }
  }
  return min;
}

void main() {
  List<int> numbers = [10, 3, 5, 7, 2];
  print(findMin(numbers)); // 2
}
4. Check if a list is sorted in ascending order
dart
Copy code
bool isSortedAscending(List<int> list) {
  for (int i = 0; i < list.length - 1; i++) {
    if (list[i] > list[i + 1]) {
      return false;
    }
  }
  return true;
}

void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  print(isSortedAscending(numbers)); // true
}
5. Count the occurrence of a specific element in a list
dart
Copy code
int countOccurrences(List<int> list, int target) {
  int count = 0;
  for (int i = 0; i < list.length; i++) {
    if (list[i] == target) {
      count++;
    }
  }
  return count;
}

void main() {
  List<int> numbers = [1, 2, 3, 2, 4, 2];
  print(countOccurrences(numbers, 2)); // 3
}
6. Find the second largest element in the list
dart
Copy code
int findSecondLargest(List<int> list) {
  int largest = list[0];
  int secondLargest = list[0];

  for (int i = 1; i < list.length; i++) {
    if (list[i] > largest) {
      secondLargest = largest;
      largest = list[i];
    } else if (list[i] > secondLargest && list[i] != largest) {
      secondLargest = list[i];
    }
  }

  return secondLargest;
}

void main() {
  List<int> numbers = [1, 3, 4, 5, 2];
  print(findSecondLargest(numbers)); // 4
}
7. Remove duplicates from a list
dart
Copy code
List<int> removeDuplicates(List<int> list) {
  List<int> uniqueList = [];
  for (int i = 0; i < list.length; i++) {
    if (!uniqueList.contains(list[i])) {
      uniqueList.add(list[i]);
    }
  }
  return uniqueList;
}

void main() {
  List<int> numbers = [1, 2, 2, 3, 4, 4, 5];
  print(removeDuplicates(numbers)); // [1, 2, 3, 4, 5]
}
8. Find the intersection of two lists
dart
Copy code
List<int> findIntersection(List<int> list1, List<int> list2) {
  List<int> intersection = [];
  for (int i = 0; i < list1.length; i++) {
    if (list2.contains(list1[i]) && !intersection.contains(list1[i])) {
      intersection.add(list1[i]);
    }
  }
  return intersection;
}

void main() {
  List<int> list1 = [1, 2, 3, 4, 5];
  List<int> list2 = [3, 4, 5, 6, 7];
  print(findIntersection(list1, list2)); // [3, 4, 5]
}
9. Rotate a list by k positions to the right
dart
Copy code
List<int> rotateRight(List<int> list, int k) {
  int n = list.length;
  k = k % n; // Handle cases where k > n
  return list.sublist(n - k) + list.sublist(0, n - k);
}

void main() {
  List<int> numbers = [1, 2, 3, 4, 5];
  print(rotateRight(numbers, 2)); // [4, 5, 1, 2, 3]
}
10. Merge two sorted lists into one sorted list
dart
Copy code
List<int> mergeSortedLists(List<int> list1, List<int> list2) {
  List<int> merged = [];
  int i = 0, j = 0;

  while (i < list1.length && j < list2.length) {
    if (list1[i] < list2[j]) {
      merged.add(list1[i]);
      i++;
    } else {
      merged.add(list2[j]);
      j++;
    }
  }

  while (i < list1.length) {
    merged.add(list1[i]);
    i++;
  }

  while (j < list2.length) {
    merged.add(list2[j]);
    j++;
  }

  return merged;
}

void main() {
  List<int> list1 = [1, 3, 5];
  List<int> list2 = [2, 4, 6];
  print(mergeSortedLists(list1, list2)); // [1, 2, 3, 4, 5, 6]
}
These questions cover a wide range of list manipulation techniques and are great for building a strong foundation in handling lists in Dart.
