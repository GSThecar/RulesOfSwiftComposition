Let's Study
=============

 Prepare
 -------------
  #### [Vocabulary](https://github.com/GSThecar/RulesOfSwiftComposition/blob/master/Vocabulary) / [Scope](https://github.com/GSThecar/RulesOfSwiftComposition/blob/master/Scope) / [Xcode](https://github.com/GSThecar/RulesOfSwiftComposition/blob/Xcode/Xcode)

### Step by Step
>#### [Variable&Constant](https://github.com/GSThecar/RulesOfSwiftComposition/commit/3f443b2934d8a0d4f7603f01cf6296b095b96ef5) / [Data_Type](https://github.com/GSThecar/RulesOfSwiftComposition/blob/master/Data_Type) / [Operator](https://github.com/GSThecar/RulesOfSwiftComposition/blob/master/Operator)

### Conditional Statements
## If Statement
범위선택이 중요하다. (하기 코드의 초등학생에관한 조건문을 먼저 사용하였다면 성인이아닌 초등학생이 출력 되었을 것)

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
모든 경우를 처리하지 못하면 default 꼭! 작성해야한다

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
if문은 방법1이 있지만, 방법2도, 3,4,5...도 있을 수 있다면, guard는 이때만 실행하고 아니면 그만둬! 라는 것 같음
