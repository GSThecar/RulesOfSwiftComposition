
# Lazy Stored Properties

## When you first acccess, passed value.

<pre><code>

struct Image {
init() {
print("new image")
}
}

struct BlogPost {
let title: String = "Title"
let content: String = "Content"
lazy var attachment: Image = Image()

let date: Date = Date()

lazy var formattedDate: String = {
let f = DateFormatter()
f.dateStyle = .long
f.timeStyle = .medium
return f.string(from: date)
}()
}
var image = Image.init() // "new image"

var post = BlogPost()
post.attachment // "new image"

</code></pre>

# Computed Properties

## By Compute, Effect to Stored Properties OR Return Result : ex) 'var'age

<pre><code>

class Person {
var name: String
var yearOfBirth: Int

init(name: String, year: Int) {
self.name = name
self.yearOfBirth = year
}
var age: Int {
get {
let calendar = Calendar.current
let now = Date()
let year = calendar.component(.year, from: now)
return year - yearOfBirth
}
set {
let calendar = Calendar.init(identifier: Calendar.Identifier.gregorian)
let now = Date.init()
let year = calendar.component(.year, from: now)
yearOfBirth = year - newValue
}
}
}

let personA = Person(name: "GSThecar", year: 1986)
personA.age // return by get {} coputed result 33
personA.age = 50 // pass to yearOfBirth property, what coptued result, by set {} 
personA.yearOfBirth // 1969

</code> </pre>

# Read Only Properties

## Can ommit Get {} 

<pre><code>

class IDCard {
var name: String
var yearOfBirth: Int

init(name: String, year: Int) {
self.name = name
self.yearOfBirth = year
}
var age: Int {
let calendar = Calendar.current
let now = Date()
let year = calendar.component(.year, from: now)
return year - yearOfBirth
}
}

</code></pre>

# Type Properties

## Valu Type: static, Reference Type: class

<pre><code>

enum Weekday: Int {
case sunday = 1, tuesday, wednesday, thursday, friday, saturday, monday

static var today: Weekday {
let cal = Calendar.current
let today = Date()
let weekday = cal.component(.weekday, from: today)
return Weekday(rawValue: weekday)!
}
}
Weekday.today // when access, use type's name

</code></pre>

# Property Observer

## Notify when change property's value

<pre><code>

class Size {
var width = 0.0 {
willSet {                                 //ommit (Size), newValue
print(width, "=>", newValue)
}
didSet {                                //ommit (Size) , oldValue
print(oldValue, "=>", width)
}
}
}

let s = Size()
s.width = 3.3

</code></pre>

