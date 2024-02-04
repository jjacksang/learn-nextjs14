<h2>2024. 01. 30</h2>
Next JS 14버전에 대하여 학습을 시작한다.</br>
Next JS 에는 가장 크게 볼 수 있는 page, layout, not-found가 있다.</br>
page는 기본적으로 보여주고 싶은 main영역을 담당하는 역할이다</br>
layout은 HTML의 구성요소를 기본적으로 title과 root render를 실행한다.</br>
not-found같은 경우 이 전에 사용할 때 알지 못했는데 404에러를 반환해주는 화면단이 기본적으로 구성되는 nextJS에 요소중 하나인 것이다.</br>
고로 이 말은 not-found error를 발견했을 때 작성자의 임의로 404에러를 발생시키는 화면을 수정할 수 있다는 뜻이다.</br>
<hr>
그리고 오늘 알게 된 또 하나의 사실은 Next JS는 JS가 필요없다는 것이다.</br>
확인하는 방법은 npm run dev를 실행시킨 후 개발자 도구에서 소스를 들어가 javascript를 끄는 것으로 확인할 수 있다</br>
그렇게 됬을 때 다시 새로고침을 하게 되면 순수 React에서는 javascript가 없어서 UI를 보여줄 수 없고 Next JS의 경우에는 새로고침을 해도 영향을 받지 않는 것이다.</br>
이유는 Next JS는 render될 시 HTML로 반환하기 떄문이었다.</br>
그렇다는 것은 이것이 SSR의 기본적인 구성을 보여주는 요소인 한 부분이라고 생각된다.</br>
React의 경우 CSR이기 때문에 Client가 어떤 장애를 겪을 시 UI단의 로딩부분이나 동작이 느려지거나 작동하지 않을 수 있는데 Next JS의 경우 그와 상관없이 Server단에서 render가 이루어지기 때문에 지장이 없다는 것이다.

<h2>2024.02.03</h2>
Next JS 에서 layout 의 기능을 알아보게 되었다.</br>
Next JS 에서는 layout을 여러 개 설정 할 수 있고 폴더마다 layout을 따로 줄 수 있었다.</br>
단, 가장 상단에 존재하는 layout을 먼저 호출하고 그 안에 자식요소로 존재하는 {children} 을 호출하여 폴더 안에 있는 다른 layout을 호출 할 수 있다.</br>
그렇게 되므로써 여러 개의 layout을 동시에 보여줄 수도 있고 쪼개서 보여주는 방법도 있다.</br>
하지만 생각지 못한 부분이 있었는데 layout이 여러 곳에서 호출될시에 첫 layout은 가장 상단의 것이 호출됬고 그 다음 layout은 {children}으로 존재하는 layout이 호출됬다.</br>
여기서 특이점은  상단에 존재하는 layout부터 쌓아올리는 방식으로 호출된다는 것이다.</br>
예를 들면 첫 layout이 호출되서 Home으로 표시한 layout이 있다면 그 안쪽에 존재하는 children안에 layout은 Home 위에 표시된다는 것이다.</br>
단순하게 stack을 쌓는 방식으로 호출되는 것을 알 수 있었다.</br>

<h2>2024.02.04</h2>
오늘 강의를 통해 배운 새로운 것이 있다.</br>
Next JS에서는 loading이라는 기능이 있고 앞 전에 이야기 했었던 layout, page, not-found와 같은 역할을 하는 것이다.</br>
loading의 경우 각 page가 존재하는 곳에 생성하면 그 폴더안에 맞게 적용되고 이는 즉시 보여주지 않고 로딩을 진행시킬때 대신 나타나는 모습이 나타나게 된다.</br>
또 다른 기능은 api와 소통하는 기능이었다.</br>
앞전에 사용했던 api기능에서는 useState로 상태를 잡아주고 useEffect로 api를 response해서 fetch 해주어야 했지만 Next JS에서는 간단하게 const URL = ...() 선언해주고 async function으로 다시 윗쪽에 선언한 URL을 받아와 fetch작업을 한 후 함수로 보여주는 단에 전달해준다는 것이었다.</br>
실제로 코드의 양이나 사용하는 시간또한 절약할 수 있었고 useState와 useEffect를 사용하지 않아도 되기 때문에 코드의 무게또한 줄었다고 볼 수 있었다.
