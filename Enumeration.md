
# Enumerations

## Enumeration Type(Container)안에 Enumeration Case(Constant)가 구성되어 있다
<pre><code>

enum Day: Int {
case monday
case tuesday
case wednesday
case thursday
case friday
case saturday, sunday
}

Day.saturday.rawValue // 5
Day.sunday.rawValue // 6

</code></pre>

## EnumuerationCasePattern

<pre><code>

enum Transportation {
case bus(number: Int)
case taxi(company: String, number: String)
case subway(lineNumber: Int, express: Bool)
}

var myTransportation = Transportation.bus(number: 22)  // 22번버스

switch myTransportation {                                                // 22
case .bus(let n):
print(n)
case .taxi(let c, _):
print(c)
case let .subway(lineNumber: ln, express: ex):
print(ln, ex)
}

myTransportation = Transportation.subway(lineNumber: 1, express: true) // 급행 1호선

if case let .subway(1, express) = myTransportation {                                  // 급행열차
if express {
print("급행열차")
} else {
print("완행열차")
}
}

</code></pre>

