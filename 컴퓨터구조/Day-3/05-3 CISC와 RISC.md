05-3 CISC와 RISC

# 명령어 집합
CPU는 수많은 제조사들이 있고, CPU마다 규격과 기능, 만듦새가 다 다르기에 모든 CPU가 이해하고 실행하는 명령어들이 다 똑같지는 않다.
명령어의 세세한 생김새, 명령어로 할 수있는 연산, 주소 지정 방식 등은 CPU마다 조금씩 차이가 있다. CPU가 이해할 수 있는 명령어들의 모음을 **명령어 집합** 또는 **명령어 집합 구조** **ISA**(Instruction Set Architecture)이라고 한다. 즉 CPU마다 ISA가 다를 수 있다는 것이다.
인텔의 노트북 속 CPU와 애플의 아이폰 속 CPU가 서로 다른 ISA를 이해하듯이 그리고 ISA가 다르다는 것은 CPU가 이해할 수 있는 명령어가 다르다는 뜻이고, 명령어가 달라지면 어셈블리어도 달라진다. 같은 소스코드로 만들어진 프로그램이라도 ISA가 다르면 CPU가 이해할 수 있는 명령어도 어셈블리어도 달라진다는 것이다.
쉽게 생각해 ISA는 일종의 CPU의 언어이다.

CPU가 이해하는 명령어들이 달라지면 즉 ISA가 달라지면 제어장치가 명령어를 해석 하는 방식, 사용되는 레지스터의 종류와 개수, 메모리 관리 방법 등 많은 것이 달라진다. 
하드웨어가 소프트웨어를 어떻게 이해할지에 대한 약속



## CISC(Complex Instruction Set Computer)
복잡한 명령어 집합을 활용하는 컴퓨터(CPU) 이름 그대로 복잡하고 다양한 명령어들을 활용하는 CPU 설계 방식이다.
CISC는 다양하고 강력한 기능의 명령어 집합을 활용하기 때문에 명령어의 형태와 크기가 다양한 가변 길이 명령어를 활용한다. 다양하고 강력한 명령어를 활용한다는 말은 상대적으로 적은 수의 명령어로도 프로그램을 실행할 수 있다는 것을 의미한다. 이 명령어 수가 적다는 것은 컴파일된 프로그램의 크기가 작다는 것을 의미한다.

### 장점
- 명령어 수가 적기에 메모리 공간을 절약할 수 있다는 장점이 있다.

### 단점
- 명령어가 워낙 복잡하고 다양한 기능을 제공하는 탓에 명령어의 크기와 실행되기까지의 시간이 일정하지 않다.
- 복잡한 명령어 때문에 명령어 하나를 실행하는 데에 여러 클럭 주기를 필요로 한다.(이는 명령어 파이프라인을 구현하는데 큰 걸림돌이 된다.)
- 복잡하고 다양한 명령어를 활용할 수는 있지만 대다수의 복잡한 명령어는 사용 빈도가 낮다.

명령어 파이프라인 기법을 위한 이상적인 명령어는 각 단계에 소요되는 시간이 동일해야 한다. CISC에서 활용하는 명령어는 수행 시간이 길고 가지각색이기 때문에 파이프라인이 효율적으로 명령어를 처리할 수 없다.



## RISC(Reduce Instruction Set Computer)
RISC에 대해 알아보기전에 CISC에서의 한계는 다음과 같았다.
1. 원할한 파이프라이닝이 쉽지 않다. -> '명렁어 길이와 수행 시간이 짧고 규격화'되어야 한다.
2. 자주 쓰이는 명령어만 줄곧 사용된다. -> 복잡한 기능을 지원하는 명령어를 추가하기보다는 '자주 쓰이는 기본적인 명령어를 작고 빠르게 만드는 것'이 중요하다.
이러한 원칙하에 등장한 것이 RISC이다. 특징으로는 CISC와 달리 짧고 규격화된 명령어, 되도록 1클럭 내외로 실행되는 명령어를 지향한다.
RISC는 **고정 길이 명렁어**를 활용한다.

### 특징
- 명령어가 규격화되어 있다.
- 하나의 명령어가 1클럭 내외로 실행된다.(파이프라이닝에 최적화 되어 있다.)
- 메모리에 접근하는 명령어를 load, store 두 개로 제한할 만큼 메모리 접근을 단순화하고 최소화를 추구한다.
- CISC보다 많은 명령으로 프로그램을 작동시킨다.
