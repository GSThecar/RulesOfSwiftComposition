
# Closures 


## 사전의미 '폐쇄', 나만의 해석 - 표현식이 브레이스로 쌓여있는 형태로 기능전달 및 수행 


<pre><code>

let c1 = { print("Hello") }

let c2 = { (name: String) -> String in
c1()
return "Nice meet you \(name)"
}
print( c2("Daivd") ) // Hello \n Nice meet you David

let list = [1, 2, 3, 4, 5]

//In Line Closure
list.filter({ (num: Int) -> Bool in
return num.isMultiple(of: 2)
}) 

//Trailing Closure
list.filter(){ (num: Int) -> Bool in
return num.isMultiple(of: 2)
} 

</code></pre>


## Syntax Optimization

<pre><code>

//Full Version
list.filter({ (num: Int) -> Bool in
return num.isMultiple(of: 2)
}) 

//Step1
list.filter(){ (num: Int) -> Bool in
return num.isMultiple(of: 2)
}

//Step2
list.filter(){ (num: Int) -> Bool in
return num.isMultiple(of: 2)
}

//Step3
list.filter(){ (num: Int) -> Bool in num.isMultiple(of: 2) }

//Step4
list.filter(){ (num: Int) in num.isMultiple(of: 2) }

//Step5
list.filter{ $0.isMultiple(of: 2) }

</code></pre>

## Escaping Closure


<pre><code>

func performNonEscaping(closure: () -> ()) {
print("start")
closure()
print("end")
}

performNonEscaping { //start closure end
print("closure")
}

func performEscaping(closure: @escaping () -> () ) {
print("start")

let a = 12

DispatchQueue.main.asyncAfter(deadline: .now() + 3) {
closure()
print(a)
}

print("end")
}

performEscaping { //start end  ... closure 12
print("closure")
}

</code></pre>
