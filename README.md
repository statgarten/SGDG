# StatGarten Design Guide

[For more information..](https://zeroheight.com/09f3d6cb7/p/72cb61-statgarten-design-guide)

## What is the SGDG?
본 디자인 시스템은 StatGarten의 디자인원칙과 UI 구성 요소의 모음입니다. 이는 색상, 폰트, 스타일과 같은 일관된 UI 요소를 제공합니다. 개발자는 이러한 구성 요소를 다양한 조합으로 재사용하여, 매번 디자인 요소를 다시 설계하는 데 쓰이는 시간을 낭비하지 않을 수 있습니다. 디자인 시스템은 '완성'되지 않습니다. StatGarten이 발전함에 따라 언제든 새로운 UX 및 UI 디자인 요소가 추가 될 수 있습니다. **결과적으로 SGDS는 전체 플랫폼을 일관성 있게 유지하고 결합하는 결합조직의 역할을 함을 목적으로 합니다.**

## Colors
### The color palette for graphs
<img width="691" alt="스크린샷 2022-10-28 오전 9 38 34" src="https://user-images.githubusercontent.com/28377612/198422776-e6f45f60-356a-45db-ad13-e5a9148a31ac.png">

```
palette <- c("#C70A80", "#37E2D5", "#FBCB0A", "#3EC70B", "#590696")

# For ggplot2 ----

iris %>% 
  ggplot(aes(Sepal.Length, Sepal.Width, color = Species)) +
  geom_point() +
  scale_color_manual(values = c("#C70A80", "#37E2D5", "#FBCB0A", "#3EC70B", "#590696"))
```

### The colors for the dashboard
<img width="689" alt="스크린샷 2022-10-28 오전 9 38 40" src="https://user-images.githubusercontent.com/28377612/198422891-ffbe160b-778d-4864-ac1c-e0f47a1a1939.png">

### The colors for denotation
<img width="683" alt="스크린샷 2022-10-28 오전 9 38 48" src="https://user-images.githubusercontent.com/28377612/198422933-d06507db-a335-4934-b3ce-ea4c81a46d8b.png">

## Typography
### Primary Font
기본 폰트는 Pretendard를 사용함을 원칙으로 합니다. 이는 SIL 오픈 폰트 라이선로 글꼴 단독 판매를 제외한 모든 상업적 행위 및 수정, 재배포가 가능합니다.  
Download the Pretendard fonts [here](https://noonnu.cc/font_page/694)

### Secondary Font
2차 폰트는 Noto Sans KR을 사용함을 원칙으로 합니다. 이는 오픈 폰트 라이센스에 따라 사용이 허가됩니다. 인쇄 또는 디지털, 상업 또는 기타 제품 및 프로젝트에서 사용할 수 있습니다.
Download the Pretendard fonts [here](https://fonts.google.com/noto/specimen/Noto+Sans+KR?query=noto+sans+kr)

```
library(dplyr)
library(ggplot2)
library(showtext)

font_add_google("Noto Sans KR", "notosanskr")
showtext_auto()

iris %>% 
  ggplot(aes(Sepal.Length, Sepal.Width, color = Species)) +
  geom_point() +
  scale_color_manual(values = c("#C70A80", "#37E2D5", "#FBCB0A", "#3EC70B", "#590696")) +
  labs(
    title = "Noto Sans KR 사용 그래프 예시",
    subtitle = "Statgarten은 보조 폰트로 Noto Sans KR을 사용합니다."
  ) +
  ggthemes::theme_fivethirtyeight(base_family = "notosanskr")
```
