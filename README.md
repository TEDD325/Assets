# Assets
- 강의에 필요한 이미지, 영상, 시각화 자료

# 디자인 스타일
────────────────────────────────────
■ 폰트
────────────────────────────────────
- 본문: 'Noto Sans KR' (wght 300/400/500/700)
- 수식·수치: 'JetBrains Mono' (wght 400/600)
- Google Fonts CDN에서 로드

────────────────────────────────────
■ 컬러 토큰 (CSS 변수)
────────────────────────────────────
:root {
  --bg:      #f5f6f8;   /* 페이지 배경 */
  --bg2:     #eef0f3;   /* 보조 배경 (인라인 코드박스 등) */
  --bg3:     #e6e8ed;   /* 슬라이더 트랙 등 */
  --card:    #ffffff;
  --border:  rgba(0,0,0,0.08);
  --border2: rgba(0,0,0,0.14);
  --text:    #1a1d24;   /* 기본 텍스트 */
  --text2:   #5a5f72;   /* 보조 텍스트 */
  --text3:   #9096a8;   /* 힌트·레이블 */
  --red:     #d93f4c;   /* 포인트 컬러 1 (강조, 슬라이더 thumb) */
  --blue:    #2878e0;   /* 포인트 컬러 2 */
  --teal:    #0fa884;   /* 포인트 컬러 3 */
  --amber:   #c97d10;   /* 포인트 컬러 4 */
  --font:    'Noto Sans KR', sans-serif;
  --mono:    'JetBrains Mono', monospace;
}

────────────────────────────────────
■ 레이아웃
────────────────────────────────────
- body: flex column, align-items center, padding 36px 20px 56px, background var(--bg)
- 콘텐츠 최대 너비: 860px
- 전체 박스 모델: box-sizing border-box

────────────────────────────────────
■ 컴포넌트 스펙
────────────────────────────────────

[formula-banner]  상단 수식 배너
  - background: var(--card), border: 1px solid var(--border2), border-radius: 12px
  - padding: 14px 24px, font-family: var(--mono), font-size: 14px, text-align: center
  - 변수명은 var(--teal), 부연 설명은 var(--text3) font-size 11px

[metric 카드]  핵심 수치 표시 (3열 grid, gap 12px)
  - background: var(--card), border: 1px solid var(--border), border-radius: 12px, padding: 16px 18px
  - 레이블: font-size 11px, color var(--text3), letter-spacing 0.04em
  - 수치: font-size 26px, font-weight 700, font-family var(--mono)
  - 수치 색상: --red / --teal / --amber 중 선택

[card]  일반 섹션 컨테이너
  - background: var(--card), border: 1px solid var(--border), border-radius: 14px, padding: 20px 24px
  - 카드 레이블: font-size 11px, font-weight 500, letter-spacing 0.09em, text-transform uppercase, color var(--text3), margin-bottom 16px

[cls-tab]  필터/탭 버튼
  - padding: 5px 16px, border: 1px solid var(--border2), border-radius: 7px
  - 기본: background transparent, color var(--text2)
  - hover: background var(--bg2), color var(--text)
  - active: background rgba(217,63,76,0.09), border-color rgba(217,63,76,0.35), color var(--red), font-weight 500
  - transition: all 0.15s

[range slider]
  - height 4px 트랙, background var(--bg3), border-radius 4px
  - thumb: width/height 18px, border-radius 50%, background var(--red), border 3px solid #fff, box-shadow 0 0 0 1.5px var(--red)
  - hover thumb: transform scale(1.15), transition 0.1s

[formula-live]  인라인 계산 과정 박스
  - background: var(--bg2), border: 1px solid var(--border), border-radius: 9px
  - padding: 13px 16px, font-family: var(--mono), font-size: 13px, color: var(--text2), line-height: 2

[chart tooltip]  Chart.js 툴팁
  - backgroundColor #ffffff, borderColor rgba(0,0,0,0.12), borderWidth 1
  - titleColor var(--text2), bodyColor var(--text)

[chart axes]
  - grid: rgba(0,0,0,0.05), border: rgba(0,0,0,0.09)
  - ticks/title: color #9096a8, font-size 11px

────────────────────────────────────
■ 인터랙션 원칙
────────────────────────────────────
- 슬라이더 조작 시 수치·차트 즉시 반영 (animation duration 0)
- 마지막 항목은 "자동" 계산값으로 표시 (opacity 0.5, 색상 var(--text3))
- 스택 바: height 28px, border-radius 7px, gap 2px, transition width 0.2s
- 반응형: max-width 600px에서 grid 2열로 축소, 일부 보조 컬럼 숨김

────────────────────────────────────
■ 전체 톤
────────────────────────────────────
교육용 데이터 시각화 / 라이트 모드 / 미니멀·클린
강조색은 --red 하나만 주력으로 사용하고, 나머지 컬러는 보조 역할.
수식과 수치는 반드시 JetBrains Mono로 표시.
