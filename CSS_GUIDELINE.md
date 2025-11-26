# CSS 작성 가이드라인

## 목적
WeDB 프로젝트의 CSS 코드 일관성과 가독성을 유지하기 위한 기준입니다.

## CSS 작성 규칙

### 1. 기본 형식
```
.class-name{property:value}
.another-class{property:value}
.third-class{property:value}
```

### 2. 상세 규칙

#### 2.1 셀렉터와 중괄호
- 셀렉터 `.class-name` 과 열기 중괄호 `{` 사이에 **띄어쓰기 없음**
- 예: `.back_title{` (O) / `.back_title {` (X)

#### 2.2 속성 작성
- 모든 CSS 속성을 **한 줄에** 이어서 작성
- 여러 속성이 있을 경우: `property1:value1;property2:value2;property3:value3`
- 속성명과 값 사이: 콜론 `:` (띄어쓰기 없음)
- 속성 간 구분: 세미콜론 `;`

#### 2.3 마지막 값
- **마지막 속성 값 뒤에는 세미콜론 붙이지 않음**
- 예: `height:60px;display:flex;background-color:#fff` (마지막에 세미콜론 없음)

#### 2.4 줄 바꿈
- 각 **CSS 규칙(셀렉터 + 속성)은 새로운 줄**에 작성
- 다음 CSS 규칙은 그 다음 줄에서 시작

### 3. 예시

#### 좋은 예시
```
.back_title{height:60px;display:flex;align-items:center;justify-content:center;position:relative;background-color:#fff}
.back_title .btn_back{position:absolute;left:20px}
.back_title .btn_back img{width:50%;height:auto}
.back_title h2{text-align:center;font-size:18px;margin:0}
.tab_menu{display:flex;width:100%;margin-top:8px;list-style:none;padding:0}
.tab_menu li{flex:1}
.tab_menu li a{display:block;height:45px;line-height:43px;background:#B0B6DA;text-align:center;color:#fff;margin-right:1px;text-decoration:none;font-size:14px;transition:all 0.2s ease;border-bottom:2px solid transparent}
.tab_menu li:last-child a{margin-right:0}
.tab_menu li a.active{background:#fff;color:#343D94;border-bottom:2px solid #343D94}
```

#### 나쁜 예시
```
.back_title {
  height: 60px;
  display: flex;
}

.back_title .btn_back {
  position: absolute;
}
```

### 4. 복잡한 셀렉터 예시
- 자식 선택자: `.parent > .child{property:value}`
- 인접 형제 선택자: `.element + .sibling{property:value}`
- 속성 선택자: `[data-icon]{property:value}`
- 부정 선택자: `.element:not(.td_title){property:value}`
- 예: `.main_table_type3 tr.last-of-rowspan td:not(.td_title){border-bottom:2px solid #92a5da}`

### 5. 의사 클래스/요소
- hover, active, focus 등의 의사 클래스 사용 가능
- 예: `.tab_menu li a:hover{background:#fff;color:#343D94}`
- 예: `.mobile_menu_list a::before{content:"menu"}`

### 6. 미디어 쿼리 (필요시)
- 미디어 쿼리도 동일한 규칙 적용
- 예: `@media (max-width:768px){.class{property:value}}`

## 파일 구조
- 모든 CSS는 `css/mobile.css`에 통합 관리
- HTML 파일에는 inline style 사용 금지
- CSS 작성 후 위 가이드라인 준수 필수

## 적용 대상
- `css/mobile.css` - 메인 스타일시트
- `css/reset.css` - 리셋 스타일시트 (별도 가이드 가능)
