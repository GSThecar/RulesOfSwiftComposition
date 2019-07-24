
# For in Loop

###  반복할 횟수가 정해져 있을때 사용한다

let arr = [1, 2, 3, 4]

for num in arr {
num
}



### Sequence, LazySequence

//[Sequence] (filter 4번) + (3, 4 map 2번) = 6번
let a = [1, 2, 3, 4]
.filter { $0 % 2 == 0 }
.map { "[\($0)]" }
print(a)

//[LazySequence] {Base[1, 2, 3, 4], PredicateFunction(filter), TransformFuction(map)}4번 = 4번
let b = [1, 2, 3, 4]
.lazy
.filter { $0 % 2 == 0 }
.map { "[\($0)]" }
print(b)
print(Array(b))


# While

### 반복할 횟수를 모르거나, 알기 어려울때 사용한다

var count = 0

while true {
guard count < 5 else { break }
print("ok")
count += 1
}

### Repeat While

var num = 100

repeat {
num += 1
print(num)
} while num < 100
