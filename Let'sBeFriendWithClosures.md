
# Just do it, again and again

## Let's make 'Filter'
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


## Sure. I don't know yet..... Tomorrow again
###  hm.... i choose 'sorted'
