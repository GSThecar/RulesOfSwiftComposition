

### If Statement
## 주의: 하기 예문의 결과는 성인이나, age > 7부분이 먼저 쓰였다면, 결과는 달라진다
<pre><code>
let age = 34
if age > 20 {
    print("성인")
} else if age > 16 {
    print("고등학생")
} else if age > 13 {
    print("중학생")
} else if age > 7 {
    print("초등학생")
} else {
    print("미취학아동")
}
</code></pre>


### Switch Statement
## 모든 경우를 표현하였다면 default는 생략가능하다

<pre><code>
let temperature = -8

switch temperature {
case ..<10:
   print("Cold")
case 11...20:
   print("Cool")
case 21...27:
   print("Warm")
case 28... :
   print("Hot")
default:
   break
}
</code></pre>

### Guard Statement
## if문은 방법1이있고, 방법2도, 3,4,5....있을 수 있다라면, guard는 condition이 true평가되는 경우만 실행, 아니면 그만둬!라는 것 같음
<pre><code>

</code></pre>
*/
