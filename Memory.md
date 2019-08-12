
# 메모리 :  코드를 통해 처리하는 모든 데이터가 저장된다.

## 비트: 정보의 최소단위, 표준 1바이트 = 8비트 단위로 주소가 부여되고 사용된다

### 참고) 32비트 CPU의 컴퓨터에 최대4GB의 메모리

<pre><code>


사용용도에따른 분류
코드 : 기계어로 번역된 프로그램 코드
데이터: 정적변수, 전역변수 프로그램 실행시 생성 및 종료시 삭제
* 힙: 동적할당 공간예측 힘듬, 코드를 작성하여 제거해야함. 메모리 누수주의*
스택: 지역변수, 파라미터, 리턴값

예시) 함수호출시 스텍프레임에 할당 함수종료시 제거 LIFO(Last in First Out)
값형식의 실제 데이터는 스택에, 참조형식의 실제 데이터는 힙에 저장된다 (참조형식: 스택에는 힙의주소)


</code></pre>

# Automatic Reference Counting

<pre><code>

class Person {
   var name = "John Doe"
   
   deinit {
      print("person deinit")
   }
}

var person1: Person?
var person2: Person?
var person3: Person?

person1 = Person()
person2 = person1
person3 = person1

person1 = nil
person2 = nil
person3 = nil // "person deinit"

</code></pre>

# Strong Reference Cycle

<pre><code>

class Person {
   var name = "John Doe"
   var car: Car?
   
   deinit {
      print("person deinit")
   }
}

class Car {
   var model: String
   var lessee: Person?
   
   init(model: String) {
      self.model = model
   }
   
   deinit {
      print("car deinit")
   }
}

var person: Person? = Person()
var rentedCar: Car? = Car(model: "Porsche")

person?.car = rentedCar
rentedCar?.lessee = person

person = nil
rentedCar = nil

</code></pre>

# Weak Reference

<pre><code>

class Person {
   var name = "John Doe"
   var car: Car?
   
   deinit {
      print("person deinit")
   }
}

class Car {
   var model: String
   weak var lessee: Person?
   
   init(model: String) {
      self.model = model
   }
   
   deinit {
      print("car deinit")
   }
}

var person: Person? = Person()
var rentedCar: Car? = Car(model: "Porsche")

person?.car = rentedCar
rentedCar?.lessee = person

person = nil //"person deinit"
rentedCar = nil //"car deinit"

</code></pre>

# Unowned Reference (Run time)

<pre><code>

class Person {
   var name = "John Doe"
   var car: Car?
   
   deinit {
      print("person deinit")
   }
}

class Car {
   var model: String
   unowned var lessee: Person?
   
   init(model: String) {
      self.model = model
   }
   
   deinit {
      print("car deinit")
   }
}

var person: Person? = Person()
var rentedCar: Car? = Car(model: "Porsche")

person?.car = rentedCar
rentedCar?.lessee = person

person = nil
rentedCar = nil

</code></pre>

# Colosure Capture list

<pre><code>

class Car {
    var totalDrivingDistance = 0.0
    var totalUsedGas = 0.0
    
    lazy var gasMileage: () -> Double? = { [weak self] in
        guard let totalDrivingDistance = self?.totalDrivingDistance,
            let totalUsedGas = self?.totalUsedGas else { return nil }
        return totalDrivingDistance / totalUsedGas
    }
    
//   lazy var gasMileage: () -> Double? = {
//    let totalDrivingDistance = self.totalDrivingDistance
//    let totalUsedGas = self.totalUsedGas
//        return totalDrivingDistance / totalUsedGas
//    }
    
    func drive() {
        self.totalDrivingDistance = 1200.0
        self.totalUsedGas = 73.0
    }
    
    deinit {
        print("car deinit")
    }
}

var myCar: Car? = Car()
myCar?.drive()
myCar = nil

myCar = Car()
myCar?.gasMileage()
myCar = nil

</code></pre>
