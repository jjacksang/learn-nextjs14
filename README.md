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
