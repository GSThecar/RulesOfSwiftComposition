
# Structure

## init 생략가능, 생성 후, ' . '(period)를 사용하여 접근

<pre><code>

struct Person {
var name: String
var age: Int

func speak(to yourName: String, myName: String) {
print("\(yourName), HI~! I'm \(myName)")
}
}

let personA = Person(name: "GSThecar", age: 34)  // 생성

let bName = "David"

personA.name                                                        // GSThecar
personA.age                                                          // 34
personA.speak(to: bName, myName: personA.name) // David, Hi~! I'm GSThecar

</code></pre>


## init을 사용한 속성지칭시 'self'사용, 메소드로 속성접근시 'mutating'


<pre><code>

struct SizeValue {

var width: Double
var height: Double

init(width: Double, height: Double) {
self.width = width
self.height = height
}

func size() -> Double {
var result : Double = 0.0
result = width * height
return result
}
mutating func reset() {
width = 0.0
height = 0.0
}
}

var sizeA =  SizeValue(width: 12, height: 34) // 생성
sizeA.size() // 408

</code></pre>


## 값 형식 (Structure, Enumeration, Tuple)

<pre><code>

struct PositionValue {
var x = 0.0
var y = 0.0
}

var value1 = PositionValue()

var value2  = value1 // value1에 저장되어 있던 값을 복사하여 value2에 저장 (복사 값이 다른 스택에 저장됨)

value2.x = 1
value2.y = 1

value1 // x: 0.0 y: 0.0
value2 // x: 1.0 y: 1.0

</code></pre>
