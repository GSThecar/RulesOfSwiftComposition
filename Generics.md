
# Generics

## Use Generic, No more make to addition that different type of data


<pre><code>


struct Color<Component> {
let red: Component
let green: Component
let blue: Component
}

let color = Color(red: 1, green: 2, blue: 3)   // Color<Int>
let color1 = Color(red: 1.1, green: 2.2, blue: 3.3)  // Color<Double>


struct Stack<T> {
var store = [T]()

mutating func push(data: T) {
store.append(data)
}

mutating func pop() -> T? {
return store.popLast()
}
}

var s = Stack<String>()
s.push(data: "one")
s.push(data: "two")
s.push(data: "three")
s.pop() // "three"

</code></pre>


# Type Constraints


<pre><code>


func swapValue<T:Equatable>(lhs: inout T, rhs: inout T) {
if lhs == rhs { return }
let tmp = lhs
lhs = rhs
rhs = tmp
print("Generic")
}
var a = 1
var b = 2
var c = "abcd"
var d = "ABCD"

//order of priority
func swapValue(lhs: inout String, rhs: inout String) {
if lhs == rhs { return }
let tmp = lhs
lhs = rhs
rhs = tmp
print("Special")
}

swapValue(lhs: &a, rhs: &b) // "Generic"
swapValue(lhs: &c, rhs: &d) // "Special"


</code></pre>


# Generic Types


<pre><code>


struct Color<T,U,V> {
var red: T
var green: U
var blue: V
}

var c = Color(red: 1, green: "2", blue: 0.0)


</code></pre>


# Associated Types


<pre><code>


protocol QueueCompatible {
associatedtype Element
func enqueue(value: Element)
func dequeue() -> Element?
}

class IntergerQueue: QueueCompatible {
typealias Element = Int

func enqueue(value: Int) {

}
func dequeue() -> Int? {
return nil
}
}

class DoubleQueue: QueueCompatible {
func enqueue(value: Double) {

}
func dequeue() -> Double? {
return nil
}
}

</code></pre>
