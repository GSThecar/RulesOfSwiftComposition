
#  Functions : 이름이 있는 Closure 

## 선언위치별 명칭: Global Scope - 함수, Local Scope - 메소드

### 함수호출 : Function'sName(ArgumentLabel )
<pre><code>
print("Hello") // 함수호출: 파라미터 총3개, 첫번째 와일드카드패턴, 나머지 두개는 기본값 설정

//함수 호출하는 함수
func test() {
print("hello")
}
test() 
</code></pre>

### 파라미터 기본값 지정가능
<pre><code>
func test2(str: String = "Swift") -> String {
return "Hello \(str)"
}
test2() // Hello Swift
test2(str: "GSThecar") // Hello GSThecar
</code></pre>

### ArgumentLabel: with / Parameter: str
func test2(with str: String) -> String {
return "Awesome \(str)"
}

test2(with: "Code") // Awesome Code
</code></pre>

### 가변파라미터 - 함수당 1개만, 파라미터 중 가급적 맨 뒤에, 기본값 지정 불가
<pre><code>
func printSum(of nums: Int...) -> Int {
var sum = 0
for num in nums {
sum += num
}
return sum
}

printSum(of: 1, 2, 5, 1, 4, 0, 12)

</code></pre>

### In-out parameter
<pre><code>
var num1 = 12
var num2 = 34

func swapNumber(_ a: inout Int, with b: inout Int) {
let tmp = a
a = b
b = tmp
}

swapNumber(&num1, with: &num2)
</code></pre>

### Nested Function
<pre><code>
func outer() -> () -> () {
func inner() {

print("inner")
}

print("outer")

return inner
}

let f = outer()

f() // outer, inner

</code></pre>
