# 排序

## 冒泡排序

```
public void bubbleSort(int[] a) {

  if (a.length <= 0) return;
  for (int i = 0; i < a.length; i++) {
    boolean flag = false;
    for (int j = 0; j < a.length-i-1; j++) {
      if(a[j] > a[j+1]) {
        int tmp = a[j];
        a[j] = a[j+1];
        a[j+1] = tmp;
        flag = true;
      }
    }
    if (!flag) break;  // 没有数据交换，提前退出
  }
}
```

## 插入排序

```Java
public void insertionSort(int[] a) {

  int n = a.length;
  if(n <= 1) return;

  for (int i = 1; i < n; i++) {
      int value = a[i];
      int j = i-1;
      for (; j >= 0 ; j--) {
          if(a[j] > value) {
              a[j+1] = a[j];
          } else {
              break;
          }
      }
      a[j+1] = value;
  }
}
```

## 选择排序

```Java
public void selectionSort(int[] a){
  int n = a.length;
  if (n <= 0) return;
  for (int i = 0; i < n; i++) {
      int minIndex = i;
      for (int j = i; j < n; j++) {
          if(a[j] < a[minIndex]) {
              minIndex = j;
          }
      }
      if(minIndex != i) {
          int tmp = a[i];
          a[i] = a[minIndex];
          a[minIndex] = tmp;
      }
  }
}
```

## 归并排序

```Java
public void mergeSort(int[] a, int low, int high) {
    if (low >= high) return;

    int mid = (low + high) >>> 1;

    mergeSort(a, low, mid);
    mergeSort(a, mid+1, high);

    merge(a, low, mid, high);
}

public void merge(int[] a, int low, int mid, int high) {

    int i = low;
    int j = mid + 1;
    int k = 0;
    int[] tmp = new int[high-low+1];

    while(i <= mid && j <= high) {
        if(a[i] <= a[j]) {
            tmp[k++] = a[i++];
        } else {
            tmp[k++] = a[j++];
        }
    }

    int start = i;
    int end = mid;
    if (j <= high) {
        start = j;
        end = high;
    }

    while (start <= end) {
        tmp[k++] = a[start++];
    }

    for (int l = 0; l < high-low+1; l++) {
        a[low+l] = tmp[l];
    }
}
```