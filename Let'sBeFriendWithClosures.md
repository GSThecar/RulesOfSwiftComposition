
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

