## Destructuring(디스트럭쳐링) : 구조분해할당

구조 분해 할당 구문은 배열이나 객체의 속성을 해체하여 그 값을 개별 변수에 담을 수 있게 하는 JavaScript 표현식입니다.

```javascript
let [a, b] = [10, 20];

console.log(a); // Expected output: 10
console.log(b); // Expected output: 20

let [a, b, ...rest] = [10, 20, 30, 40, 50];
console.log(rest);
// Expected output: Array [30, 40, 50]
```
