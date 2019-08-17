
# Purpose: needs of experienced about class

## Let's make game that when i was 12, enjoyment


<pre><code>

class 평민 {
var HP: Int
var MP: Int

init(HP: Int = 100, MP: Int = 100) {
self.HP = HP
self.MP = MP
}

func 후려치기(target: 평민) {
MP = MP - 10
target.HP -= 20
}
}

class 전직: 평민 {
private let name: String

override var HP: Int {
didSet {
guard HP <= 0 else { return }
print("패배자 \(name)")
}
}

init(HP: Int, MP: Int, name: String) {
self.name = name
super.init()
self.HP += HP
self.MP += MP
}

func fight(with: 전직, skill: (전직) -> Void) {
while with.HP > 0 {
skill(with)
}
}
}

final class 도적: 전직 {
init(name: String) {
super.init(HP: 200, MP: 100, name: name)
}

func 필살검무(target: 평민) {
MP -= 5
target.HP -= 50
}
}



final class 주술사: 전직 {
init(name: String) {
super.init(HP: 100, MP: 200, name: name)
}

func 에너지볼트(target: 평민) {
MP -= 20
target.HP -= 60
}

override func 후려치기(target: 평민) {
target.HP -= 10
}
}

func playGame() {
let a = 주술사(name: "술사")
let b = 도적(name: "도적")
let c = 주술사(name: "주술사")
let d = 도적(name: "도둑")

b.fight(with: d, skill: b.후려치기(target:))
a.fight(with: c, skill: a.에너지볼트(target:))
}

playGame()

</code></pre>

