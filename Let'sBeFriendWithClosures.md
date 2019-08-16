
# Just do it, again and again

## Let's make 'filter'
### my opnion : Input - Element in container, Estimation Process - Bool, Output - Result of true


<pre><code>

func imitationFilter<T>(target: [T], _ boolean: ( (_ element: T) -> Bool) ) -> [T] {
var temporaryBox: [T] = []

for elem in target {
guard boolean(elem) else { continue }
temporaryBox.append(elem)
}
return temporaryBox
}

</code></pre>


## Let's make 'sorted'
### I thought about 'sorted' that swapping according to ordered comparisons

<pre><code>

extension Array {
    func mySorted(by areIncreasing : (Element,Element) -> Bool ) -> [Element] {
        var temporarybox: [Element] = self
        
        for i in 0...self.count -1 {
            for j in 1...self.count -1 {
                guard areIncreasing(self[i], self[j]) == false else {continue}
                temporarybox.swapAt(i, j)
            }
        }
        return temporarybox
    }
}

</code></pre>


## Let's make map
### Start the Question that 'What is map?', Until about 'Functor' and 'Monad'
#### First Make it (optional..)
<pre><code>

func imitaionMap<T>(target: [T], by transform: (T) -> Any) -> [Any] {
    var temporaryBox: [Any] = []
    
    for element in target {
        let transformedElement = transform(element)
        temporaryBox.append(transformedElement)
   
    }
    return temporaryBox
}

</code></pre>

# After study by [Monad?](https://tv.naver.com/v/5340169)

## ◎ map: return content transformed in present's context, result return functor
## ◎ When content is functor, happen to problem  
## ◎ So, solution is use to flatMap that's Monad~! 

### Let's Again make Map
<pre><code>

extension Array {
    func imitaionMap<T>(_ transform: (Element) -> T ) -> [T] {
        var future: [T] = []
        
        for element in self{
        
            future.append(transform(element))
            
        }
        
        return future
    }
}

</code></pre>
