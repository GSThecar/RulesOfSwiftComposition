
# Class Type

## 초기값을 지정하지 않았다면 'init' 필수

<pre><code>

class SizeValue {

var width: Double = 0
var height: Double = 0

//    init(width: Double, height: Double) {
//        self.width = width
//        self.height = height
//    }

func size() -> Double {
var result : Double = 0.0
result = width * height
return result
}

func reset() {
width = 0.0
height = 0.0
}
}

let classA = SizeValue()
classA.width = 2
classA.height = 4


</code></pre>


# IdentityOperator

## classInstance === classInstance : Identical to Operator
## classInstance !== classInstance : Not Identical to Operator


<pre><code>

class SizeValue {

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

func reset() {
width = 0.0
height = 0.0
}
}

let classA = SizeValue(width: 0.0, height: 0.0)
let classB = classA
let classC = SizeValue(width: 0.0, height: 0.0)

classA === classB /true
classA === classC /false
classC === classB /false

</code></pre>


# 참조 형식 ( Class, Closure )

## 힙에 저장되고 스택에는 힙의 주소가 저장된다 

<pre><code>

class PositionObject {
var x = 0.0
var y = 0.0
}

var classA = PositionObject()
var classB = classA

classB.x = 1
classB.y = 1

classA // x: 1.0, y: 1.0
classB // x: 1.0, y: 1.0

</code></pre>

