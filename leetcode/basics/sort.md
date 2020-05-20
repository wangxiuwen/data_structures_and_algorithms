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