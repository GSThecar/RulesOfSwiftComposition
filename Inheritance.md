
# Inheritance 


## Reference Type able to Inherit


<pre><code>

class Figure {
var name = "Unknown"

init(name: String) {
self.name = name
}

func draw() {
print("draw \(name)")
}
}

class Circle: Figure {
var radius = 0.0
}

let c = Circle(name: "Circle")
c.draw() // "draw Cicle"

</code></pre>


# Final Class

## No more child class 

<pre><code>

class PersonA {
var name: String

init(name: String) {
self.name = name
}
}

final class PersonB: PersonA {
var age: Int

init(name: String, age: Int) {
self.age = age
super.init(name: name)
}
}

//class PersonC: PersonB{ }


</code></pre>

# Overriding

## StoredProperty is impossible

<pre><code>

class Figures {
var name: String

init(name: String) {
self.name = name
}

func draw() {
print("Draw \(name)")
}
}

class Rectangle: Figures {
override var name: String {                 //Only ComputedProperty
get {return "Rectangle"}
set {super.name = newValue}
} //only computed
}

</code></pre>
