
# Array Type : 순서가 보장되며 중복된 요소가 있을 수 있다

## Array< T >, [T]

<pre><code>

var array1: Array<Int> = [1, 2, 3]
let array2: [String] = ["A", "B"]
let array3 = [1.1, 2.2, 3.3, 4.4]

array1.count // 3
array2.isEmpty // false

array1.append(4) // [1, 2, 3, 4]

array1.insert(0, at: 0) // [0, 1, 2 ,3 ,4]

//subscript Syntax
array2[0] // A

</code></pre>


# Dictionary Type : Key & Value의 쌍으로 이루어져있다

## Dictionary<K,V>, [K:V]


<pre><code>

let dict1: Dictionary<String, Int> =  [ "a": 1, "b": 2, "c": 3 ]
let dict2: [Int: Int] = [1: 1, 2: 2, 3: 3, 4: 4]
let dict3 =  [ "A": 1, "B": 2, "C": 3 ]

dict3.count // 3
dict3.isEmpty / False

var words = [String: String]()

words["A"] = "Apple"
words["B"] = "Banana"

words.count // 2
words // ["A": "Apple", "B": "Banana"]

words["B"] = "Ball"
words // ["A": "Apple", "B": "Ball"]

words.updateValue("City", forKey: "C")

words.updateValue("Camera", forKey: "C") // insert + Update -> Upsert


</code></pre>


# Set Type : 중복없는 요소로 이루어져 있다

## Set< T >

<pre><code>

let set: Set<Int> = [1, 2, 2, 3, 3, 3]

set.count // 3
set.isEmpty // false
set.contains(4) //false

var words = Set<String>() //Set([])

words.insert("Swift") // inserted:true, memberAfterInsert:"Swift"
words // {"Swift"}

words.insert("Swift") // inserted:false, memberAfterInsert:"Swift"
words // {"Swift"}


</code></pre>
