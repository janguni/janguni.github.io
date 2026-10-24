---
layout: post
title: "배열"
date: 2026-10-24 09:00:00 +0900
categories: Java
---

> 같은 자료형의 데이터를 연속적으로 저장하는 공간

## 배열의 확장

배열의 크기는 선언과 동시에 정해져야 한다.
만약 크기를 늘리고 싶다면, 새로운 배열을 원하는 크기만큼 새로 생성한 후 기존 배열을 복사해야한다.
가능은 하지만 비용이 발생하기 때문에, 크기를 가늠할 수 있다면 애초부터 큰 크기로 선언해주는게 좋다.

### 배열 확장 과정

1. JVM이 메모리에서 연속된 빈 메모리 공간 찾기
2. 배열 복사 (O(n))
3. 기존 배열은 GC(가비지 컬렉터)로 보내짐

### 배열 확장 방법

java.util.Arrays 라이브러리 사용
Arrays.copyOf()를 사용해서 복사하면 된다.

```java
import java.util.Arrays;

int[] smallArray = {1, 2, 3};
int[] bigArray = Arrays.copyOf(smallArray, 6);
```

## 배열 초기값

크기만 지정한 배열의 초기값은 다음과 같다.

- int: 0
- double: 0.0
- String: null
- char: \u0000 (유니코드 0번)
- boolean: false

## 배열의 모든값 통일

Arrays.fill()을 사용하면 된다.

```java
import java.util.Arrays;

boolean arr = new boolean[3];
Arrays.fill(arr, true);
```

## 배열 정렬

Arrays.sort() 사용하면된다.

```java
import java.util.Arrays;
import java.util.Collections;

booelan[] s = {"b", "ab", "ac"};

// 1. 오름차순 정렬
Arrays.sort(s); // ["ab", "ac", "b"]
// 2. 내림차순 정렬
Arrays.sort(s, Collections.reverseOrder()); // ["b", "ac", "ab"]

```

## 2차원 배열

int[][] arr = new int[3][4] 이렇게 선언했다면 행이 3, 열이 4이다.

```java
int[][] arr = new int[3][4]; // 행: 3, 열: 4

arr = new int[][] {
    {0, 1, 2, 3},
    {0, 1, 2, 3},
    {0, 1, 2, 3}
};
```
