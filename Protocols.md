
# Protocol Syntax

## It's like a shell that with only minimal requirements.


<pre><code>


protocol Something {
var a: Int { get set }
func doSomething(_ :Int) -> String
init()
}

protocol MyEquatable {
var b: Int { get set }

}

struct someStruct: Something, MyEquatable {
var a: Int = 0
var b: Int = 0
func doSomething(_: Int) -> String {
return "\(a), \(b)"
}
}


</code></pre>


## Class-only protocols

<pre><code>


protocol SomethingObject: AnyObject, Something {

}

class Object: SomethingObject {
var a: Int
required init() {
a = 0
}
func doSomething(_: Int) -> String {
return "\(a)"
}
}


</code></pre>


## Protocol Types


<pre><code>


protocol Resettable {
func reset()
}

class Size: Resettable {
var width = 0.0
var height = 0.0

func reset() {
width = 0.0
height = 0.0
}
}

let someSize = Size()

let otherSize : Resettable = someSize

otherSize.reset()
//otherSize.width


</code></pre>


## Collections of Protocol Types


<pre><code>


protocol Figure {
func draw()
}

struct Triangle: Figure {
func draw() {
print("draw triangle")
}
}

class Rectangle: Figure {
func draw() {
print("draw rect")
}
}

struct Circle: Figure {
var radius = 0.0

func draw() {
print("draw circle")
}
}

let t = Triangle()
let r = Rectangle()
let c = Circle()

let arr: [Figure] = [t, r, c]

for element in arr {
element.draw()
guard let c = element as? Circle  else { continue }
c.radius
}


</code></pre>
