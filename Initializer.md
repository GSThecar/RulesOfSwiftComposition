
# Default Initializer


<pre><code>

struct Size {
let width : Double
let height: Double

init() {
width = 0.0
height = 0.0
}

init(width: Double = 0.0, height: Double = 0.0 ) {

self.width = width
self.height = height
}
}

let s = Size() 

</code></pre>


# Required Initializer 


<pre><code>

class SomeObject {
var name: String

required init(name: String) {
self.name = name
}
}

class ObjectSize: SomeObject {
var width: Double
var height: Double

required init(name: String) {
self.width = 0.0
self.height = 0.0
super.init(name: name)
}

init(width: Double, height: Double) {

self.width = width
self.height = height
super.init(name: "GSThecar")
}

</code></pre>

# Initializer Deligation


<pre><code>

convenience init(_ width: Double) {
self.init(width: width, height: 0.0)
}

convenience init?(value: Double) {
guard value >= 0 else {return nil}
self.init(width: value, height: value)
}

deinit {
// me
print("deinit")
}
}

var oS = ObjectSize(width: 0.0, height: 0.0)

oS = ObjectSize(width: 1.1, height: 2.2)

</code></pre>
