
# Instance Method 


## Function In Container {}, Calling: IstanceName.InstanceMethod


<pre><code>

class Sample {
var data = 0
static var shareData = 123

func doSomething() {
print(data)
Sample.shareData
}

func call() {
doSomething()
}

}

let sampleA = Sample()

sampleA.doSomething()
sampleA.call()
sampleA.data

struct Size {
var width = 0.0
var height = 0.0

mutating func enlarge() {
width += 1
height += 1
}
}

var sizeA = Size()

sizeA.enlarge()


</code></pre>


# Type Method

## Declaration: Use static, class key word, Calling: TypeName.TypeMehod 

<pre><code>

class CircleA {
static let pi = 3.14
var radius = 0.0

func getArea() -> Double {
return radius * radius * CircleA.pi
}

class func printPi() {
print(pi)
}
}

CircleA.printPi()

struct CircleB {
static let pi = 3.14
var radius = 0.0

func getArea() -> Double {
return radius * radius * CircleB.pi
}

static func printPi() {
print(pi)
}
}

CircleB.printPi()


</code></pre>

# Subscript

## Declarable in Classes, Enumerations, Structures with subscript key word. Also, there are ReadOnly

<pre><code>

class List {
var data = [1, 2, 3]

subscript(_ index: Int) -> Int {
get {
return data[index]
}
set {
data[index] = newValue

}
}
}

let listA = List()

listA[2]  //  3 (Element in data Array at indexNumber is 2)
listA[2] = 4


</code></pre>
