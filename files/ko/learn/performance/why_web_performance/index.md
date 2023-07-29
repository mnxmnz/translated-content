---
title: 웹 성능이 중요한 "이유"
slug: Learn/Performance/why_web_performance
i10n:
  commitSource: bb026bcb88b7f45374d602301b7b0db5a49ff303
---

{{LearnSidebar}}{{NextMenu("Learn/Performance/What_is_web_performance", "Learn/Performance")}}

웹 성능은 느린 처리 속도를 빠르게 보이게 하는 것을 포함해 웹사이트를 빠르게 만드는 모든 것입니다. 이 기사에서는 왜 웹 성능이 사이트 방문자와 당신의 사업적 목표에 중요한지 소개합니다.

<table>
  <tbody>
    <tr>
      <th scope="row">사전 지식:</th>
      <td>
        기본 컴퓨터 활용능력,
        <a
          href="/ko/docs/Learn/Getting_started_with_the_web/Installing_basic_software"
          >기본 소프트웨어 설치</a
        >,
        <a href="/ko/docs/Learn/Getting_started_with_the_web"
          >클라이언트 사이드 웹 기술들</a
        >의 기본적인 지식.
      </td>
    </tr>
    <tr>
      <th scope="row">목표:</th>
      <td>
        좋은 사용자 경험을 위해 왜 웹 성능이 중요한지 기본적으로 숙지할 수 있습니다.
      </td>
    </tr>
  </tbody>
</table>

웹 성능은 웹 브라우저에서 얼마나 빠르게 사이트의 컨텐츠가 **불러와지고** **렌더링** 되는지 그리고 사용자 상호작용에 얼마나 잘 응답하는지를 나타냅니다. 나쁜 성능을 가진 사이트는 느리게 보여지고 입력에 느리게 응답합니다. 나쁜 성능의 사이트는 사이트 이탈을 증가시킵니다. 최악의 경우 나쁜 성능은 컨텐츠가 완전히 접근 불가능하게 될 수 있습니다. 웹 성능을 위한 좋은 목표는 사용자들이 성능에 대해 느끼지 못하는 것입니다. 사이트 성능의 개인적인 인식은 주관적이지만, 로딩 및 렌더링은 측정될 수 있습니다. 좋은 성능은 대부분 사이트 방문자들에게 명백하지 않을 수 있습니다. 하지만 느린 사이트는 대부분 즉시 알아챌 수 있을 것입니다. 이것이 바로 우리가 웹 성능에 대해 신경 쓰는 이유입니다.

## 성능에 신경 쓰는 이유는 무엇일까요?

웹 성능과 관련된 모범 사례들은 웹사이트 방문자들이 좋은 경험을 갖게 하기 위해 필수적입니다. 어떤 의미에서 웹 성능은 [웹 접근성](/ko/docs/Learn/Accessibility)의 하위 집합으로 간주될 수 있습니다. 웹 접근성과 마찬가지로, 성능도 사이트 방문자들이 사이트에 접근하기 위해 어떤 디바이스를 사용하는지와 디바이스 연결 속도를 고려합니다.

예를 들어, CNN.com의 로딩 경험을 생각해 보세요. 이 글을 작성할 당시 파일 크기가 22.6MB가 넘고 400번 이상의 HTTP 요청을 했습니다.

- 광섬유 네트워크에 연결된 데스크탑 컴퓨터에서 불러온다고 상상해 보세요. 이렇게 하면 파일 사이즈에 거의 관계없이 상대적으로 속도가 빠를 것입니다.
- 대중교통에서 출퇴근 하는동안 9년된 아이패드에서 테더링된 모바일 데이터를 사용해서 같은 사이트를 불러온다고 상상해 보세요. 그 사이트는 아마 불러오는 속도가 느려지고 셀 커버리지에 따라 사용할 수 없는 상태가 될 수도 있습니다. 불러오는 것이 끝나기도 전에 포기할 수도 있습니다.
- 같은 사이트를 커버리지가 제한적이거나 아예 없는 인도 시골의 35달러 화웨이 장비에서 불러온다고 상상해 보세요. 아마 사이트는 매우 느리게 불러와질 것이고, 로딩이 되더라도 차단된 스크립트로 인해 시간이 초과될 수 있고, 로딩이 되더라도 CPU에 나쁜 영향을 끼쳐 브라우저가 종료될 수 있습니다.

사이트의 크기가 22.6 MB인 경우 3G 네트워크에서 불러오는데 83초까지 걸릴 수 있습니다. [`DOMContentLoaded`](/ko/docs/Web/API/Document/DOMContentLoaded_event) (사이트의 기본 HTML 구조를 의미) 의 경우 31.86초가 소요됩니다.

그리고 다운로드를 하는데 걸리는 시간만이 중요한 문제가 아닙니다. 많은 나라들은 여전히 인터넷 연결이 메가바이트 단위로 가격이 부과됩니다. 22.6 MB CNN.com 사이트를 예로들면, 다운로드 하는데 인도인 평균 하루 임금의 약 11%를 지출하게 됩니다. 북서 아프리카의 모바일 장치에서 이 사이트를 이용하려면 평균 임금의 이틀치 비용이 들 수 있습니다. 그리고 이 사이트를 미국의 국제 로밍 요금제로 이용한다면 어떨까요? 그 비용에 누구라도 울음을 터뜨릴 것입니다. ([다운로드 하는데 얼마나 가격이 드는지](https://whatdoesmysitecost.com/) 확인해보세요.)

### 전환율 향상시키기

사이트의 다운로드 및 렌더링 시간을 줄이면 사용자 유지율 및 전환율이 향상됩니다.

**전환율**은 사이트 방문자들이 측정된 행동 또는 원하는 행동을 수행하는 비율을 말합니다. 예를 들어 제품을 구매하거나 기사를 읽는 것 또는 뉴스레터를 구독하는 것일 수 있습니다. 전환율로 측정되어지는 이 행동은 웹사이트의 사업적 목표에 따라 달라집니다.

성능은 전환율에 영향을 줍니다. 웹 성능을 개선하면 전환율이 향상됩니다. 사이트 방문자들은 사이트를 불러오는데 2초 또는 그 이하를 기대합니다. 때때로 모바일(일반적으로 더 오래 걸리는)의 환경에서 더 빠르기를 기대하기도 합니다. 이러한 사이트 방문자들은 3초 정도에 느린 사이트를 떠나기 시작합니다.

사이트 로딩 속도도 한 가지 요소입니다. 만약 사이트가 사용자 상호작용에 느리게 반응하거나 불안정하게 표시되면, 사이트 방문자들의 흥미와 신뢰를 잃게 됩니다.

여기 성능 개선의 몇몇 실제 사례들이 있습니다.

- [Tokopedia는 렌더링 시간을 3G 연걸 시 14초에서 2초로 줄였습니다. 그리고 방문자의 19% 증가, 전체 세션의 35% 증가, 새로운 사용자의 7% 증가, 활성 사용자의 17% 증가 및 사용자당 세션들이 16% 증가했습니다.](https://wpostats.com/2018/05/30/tokopedia-new-users.html)
- [성능을 위해 Pinterest 페이지들을 재구축한 결과 대기 시간의 40% 감소, SEO 트래픽의 15% 증가 및 회원가입 전환율이 15% 증가했습니다.](https://wpostats.com/2017/03/10/pinterest-seo.html)

사람들이 사용하고 싶어 하는 웹사이트와 애플리케이션을 구축하고, 사이트 방문자들을 유치하고 유지하려면 사용자 경험이 좋은 접근성 있는 사이트를 만들어야 합니다. 웹사이트를 구축하려면 일반적으로 이미지나 비디오 같은 이진 파일 유형을 포함하여 HTML, CSS, Javascript 가 필요합니다. 당신이 사이트를 구축할 때 내리는 결정 및 도구 선택은 완성된 결과물의 성능에 큰 영향을 줄 수 있습니다.

좋은 성능은 자산입니다. 나쁜 성능에는 책임이 따릅니다. 사이트 속도는 이탈률, 전환율, 수익, 사용자 만족 및 검색 엔진 순위에 직접적인 영향을 줍니다. 성능이 우수한 사이트는 방문자 유지율과 사용자 만족도를 높이는것으로 나타났습니다. 느린 컨텐츠는 사이트 이탈로 이어지고 일부 사용자들은 다시는 돌아오지 않는 것으로 나타났습니다. 클라이언트와 서버 간의 전송되는 데이터의 양을 줄이면 모든 당사자들의 비용이 줄어듭니다. HTML/CSS/JavaScript 및 미디어 파일들의 사이즈를 줄이는 것은 사이트의 불러오는 시간과 전력 소비가 모두 줄어듭니다. ([성능 예산](/ko/docs/Web/Performance/Performance_budgets)을 확인해 주세요.)

성능을 추적하는것은 중요합니다. 네트워크 속도 및 디바이스 기능들을 포함하여 다양한 요인이 성능에 영향을 미칩니다. 단일 성능 지표는 없습니다. 그리고 비즈니스 목표가 다르면, 사이트가 지원하는 조직이나 사이트의 목표와 더 관련 있는 지표가 다를 수 있습니다. 사이트의 성능이 어떻게 인식되는지는 사용자 경험입니다!

## 결론

웹 성능은 접근성뿐만 아니라 조직 또는 비즈니스의 목표에 부합하는 다른 웹사이트 지표에도 중요합니다. 웹 사이트 성능의 좋고 나쁨은 유저 경험뿐만 아니라 대부분의 사이트의 전반적인 효율성과도 밀접하게 관련되어 있습니다. 이것이 당신이 웹 성능에 신경 써야 하는 이유입니다.

{{NextMenu("Learn/Performance/What_is_web_performance", "Learn/Performance")}}