

## If Statement
#### 주의: 하기 예문의 결과는 성인이나, age > 7부분이 먼저 쓰였다면, 결과는 달라진다
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


## Switch Statement
#### 모든 경우를 표현하였다면 default는 생략가능하다

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

## Guard Statement
#### if문은 방법1이있고, 방법2도, 3,4...있을 수 있다라면, guard는 condition이 true평가되는 경우만 실행, 아니면 그만둬!라는 것 같음

<pre><code>
var socks: Array<Int> = [1, 2, 1, 1, 2, 1, 3]
var sameColorIndex: Int = 0
var pairCount: Int = 0

for leftHand in socks {
    guard socks.count > 1, socks.count > sameColorIndex else { break } //비교 대상이없거나, 인덱스가 초과함을 방지(기존 if문 사용했었음)
    socks.removeFirst()
    
    for rightHand in socks {
        if leftHand == rightHand {            //같은색일경우
            pairCount += 1                    //켤레를 셈
            socks.remove(at: sameColorIndex) //중복방지 해당 양말삭제
        } else {
            sameColorIndex += 1              //다른색일경우 >> 이동
        }
    }
    
    print("\(leftHand)는 \((pairCount + 1)/2)켤레가 있습니다")
    pairCount = 0 //다음 색의 양말을 찾기위한 초기화
    sameColorIndex = 0 //상동
}
</code></pre>
