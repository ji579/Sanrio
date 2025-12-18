# Sanrio Website

Sanrio Korea 공식 웹사이트의 레이아웃과 구조를 분석해서 만든 프로젝트입니다.

[Live Demo](https://ji579.github.io/Sanrio/) | [GitHub](https://github.com/ji579/Sanrio.git)

---

## 프로젝트 목적

실제 운영 중인 Sanrio Korea 사이트를 보면서 레이아웃 구조와 네비게이션 설계를 공부하기 위해 시작했습니다.  
원본은 여러 페이지로 구성되어 있지만, 이 프로젝트에서는 주요 레이아웃 구현에 집중해서 단일 페이지로 제작했습니다.

브랜드의 밝고 친근한 느낌을 유지하면서 HTML/CSS 퍼블리싱 기본기를 다지는 것이 목표였습니다.

---

## 구현 내용

**레이아웃**
- 헤더, 메인 콘텐츠, 푸터 영역 구분
- Flexbox로 캐릭터 카드 그리드 배치
- 이미지 중심 구성으로 캐릭터 소개에 집중

**스타일링**
- Sanrio 브랜드 컬러 (핑크, 파스텔톤) 적용
- 귀여운 느낌을 주는 둥근 모서리와 부드러운 그림자
- 호버 시 카드가 살짝 떠오르는 효과

**인터랙션**
- 버튼과 이미지에 hover 효과
- JavaScript로 간단한 이미지 확대 기능
- 스크롤 시 부드러운 애니메이션

---

## 기술 스택

**HTML5**  
각 섹션을 의미에 맞게 구분했습니다. `<header>`, `<main>`, `<section>` 등 시맨틱 태그를 사용해서 페이지 구조를 명확하게 만들었습니다.

**CSS3**  
Flexbox로 캐릭터 카드 배치를 처리했습니다. 반복되는 스타일은 클래스로 만들어서 재사용했고, CSS 변수로 브랜드 컬러를 관리했습니다.

```css
:root {
  --sanrio-pink: #FF69B4;
  --sanrio-blue: #87CEEB;
  --card-shadow: 0 4px 12px rgba(0,0,0,0.1);
}
```

**JavaScript (ES6)**  
이미지 클릭 시 확대, 간단한 슬라이더 같은 기본적인 동적 요소를 구현했습니다. 복잡한 라이브러리 없이 바닐라 JavaScript로만 작성했습니다.

---

## 주요 구현 사항

### 1. 캐릭터 카드 레이아웃
```css
.character-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
}

.character-card {
  flex: 0 0 calc(25% - 18px);
  transition: transform 0.3s ease;
}

.character-card:hover {
  transform: translateY(-8px);
}
```
Flexbox로 카드를 균등하게 배치하고, 화면 크기에 따라 자동으로 줄바꿈되도록 했습니다. 호버 시 위로 살짝 올라가는 효과를 줘서 인터랙티브하게 만들었습니다.

### 2. 반응형 디자인
```css
@media (max-width: 1024px) {
  .character-card {
    flex: 0 0 calc(33.333% - 16px);
  }
}

@media (max-width: 768px) {
  .character-card {
    flex: 0 0 calc(50% - 12px);
  }
}

@media (max-width: 480px) {
  .character-card {
    flex: 0 0 100%;
  }
}
```
데스크톱에서는 4열, 태블릿에서는 3열, 모바일에서는 1열로 카드가 배치됩니다.

### 3. 코드 재사용성
같은 스타일이 반복되는 버튼이나 카드는 공통 클래스로 만들어서 관리했습니다.
```css
.btn-primary {
  padding: 12px 24px;
  background: var(--sanrio-pink);
  border-radius: 24px;
  transition: all 0.3s ease;
}
```
나중에 색상이나 크기를 바꿀 때 한 곳만 수정하면 되도록 설계했습니다.

---

## 배운 점

**레이아웃 분석 능력**  
실제 사이트를 보면서 어떤 구조로 만들어졌는지 파악하는 연습을 했습니다. 개발자 도구로 요소를 하나씩 확인하면서 레이아웃 방식을 이해했습니다.

**Flexbox 활용**  
그리드 배치를 Flexbox로 구현하면서 `flex-basis`, `gap`, `flex-wrap` 같은 속성을 실전에서 사용해봤습니다.

**일관성 있는 스타일링**  
브랜드의 톤앤매너를 유지하면서 전체 페이지의 스타일을 통일하는 게 생각보다 중요하다는 걸 알게 됐습니다. CSS 변수를 사용하니 색상 관리가 훨씬 편했습니다.

---

## 아쉬운 점 & 개선 방향

- 원본 사이트에 있는 복잡한 메뉴 구조는 구현하지 못했습니다
- 이미지 최적화가 부족해서 로딩 속도를 더 개선할 필요가 있습니다
- JavaScript 인터랙션을 더 다양하게 추가하고 싶습니다

다음에는 더 복잡한 네비게이션과 페이지 전환 효과를 구현해보려고 합니다.

---

## 프로젝트 구조

```
Sanrio/
├── index.html
├── css/
│   ├── reset.css
│   └── style.css
├── js/
│   └── main.js
└── images/
    └── characters/
```

---

## 라이선스

이 프로젝트는 학습 목적으로 제작되었습니다.  
Sanrio 브랜드 및 캐릭터의 저작권은 (주)산리오에 있습니다.