
# Optional Type

###  nil이라는 '값이 없음'을 나타냄을 갖을수 있는 형식
<pre><code>
let nonOptional: String = "Swift"
let optional: Optional<String> = nil

print(optional)  // nil

let number: Int = 123
let otherNumber: Int? = nil
</code></pre>

### Forced Unwrapping '!',  값이 있음을 보장한다면 문제가 없다
<pre><code>
let optionalNumber: Int? = 123

let before = optionalNumber
let after = optionalNumber!

print(before) // optional(123)
print(after) // 123
</code></pre>

### Optional Binding 값의 유무를 확인하고 사용하기때문에 상대적으로 안전하다

<pre><code>
let optionalNumber: Int? = 123

if let number = optionalNumber {
print(number) // 123
}

let list: [Int?] = [0, nil, nil, 3, nil, 5]

for element in list {
guard let number = element else { continue }
print(number)
}

for case let x? in list {
print(x)
}

let a: Int? = 123
let b: String? = "String"

if let num = a, let str = b, str.count > 6 { 
print(num, str) 
}
</code></pre>

### Nil-Coalescing Operator 
<pre><code>
var msg = ""
var input: String? = "Swift"

if let inputName = input {
msg = "Hello, " + inputName
} else {
msg = "Hello, Stranger"
}

print(msg)

var str = "Hello, " + (input != nil ? input! : "Stranger")

print(str)

str = "hello, " + (input ?? "stranger")
print(str)

 //주의)다음과 같은 형식으로 코딩할때, input에 따라 뒤 문이 실행되고 안되고 결정됨
input = nil
str = "hello, " + (input ?? "stranger")
print(str)

</code></pre>


### Optional Chainning
<pre><code>
struct Contacts {
var email: [String: String]?
var address: String?

func printAddress() {
print(address ?? "no address")
}
}

struct Person {
var name: String
var contacts: Contacts?

init(name: String, email: String) {
self.name = name
contacts = Contacts(email: ["home": email], address: "Seoul")
}
}

var personA = Person(name: "GSThecar", email: "thecar3774@gmail.com")
var personB = Person(name: "Bbo", email: "bytiger@hanmail.com")

personA.contacts?.printAddress() // Seoul출력

personA.contacts = nil

personA.contacts?.printAddress() // contacts에서 중지

</code></pre>

### I.U.O(암시적추출옵셔널)
<pre><code>
let num: Int! = 12

let a = num

let b: Int = num
</code></pre>
