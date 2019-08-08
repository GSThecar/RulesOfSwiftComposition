
# Extensions

## Used when extend to existing 'type'
### Properties, Methods, Initializer, subscript, NestedType

<pre><code>
extension Date {
var year: Int {
let cal = Calendar.current

return cal.component(.year, from: now)
}

var day: Int {
let cal = Calendar.current

return cal.component(.day, from: now)

}

func toString() -> String {
let formatter = DateFormatter()
formatter.dateStyle = .full
formatter.timeStyle = .none
formatter.dateFormat = "yyyy년 m월 d일"
formatter.locale = Locale(identifier: "ko_kr")
return formatter.string(from: self)
}

subscript(component: Calendar.Component) -> Int? {
let cal = Calendar.current
return cal.component(component, from: now)

}
}

let now = Date()

now.year
now[.hour]

</code></pre>



## Also, used when Inherit class, protocol

<pre><code>
struct Size {
var width = 0.0
var height = 0.0

var m3: Double
}

extension Size {
var m2: Double { return width * height }
}

extension Size: Equatable {
public static func == (lhs: Size, rhs: Size) -> Bool {
return lhs.width == rhs.width && lhs.height == rhs.height
}
}

let a = Size(width: 12, height: 34, m3: 100)
let b = Size(width: 12, height: 34, m3: 99)

a == b // true, ignore m3

</code></pre>

