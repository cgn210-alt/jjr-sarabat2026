# jjr-sarabat2026 — 2026 사르밧 프로젝트 (감사의 쌀 나눔)

중종로공동체 추수감사절 쌀 나눔 헌금 캠페인. 34개 순의 입금 현황을 실시간으로 보여주는 공개 현황판과, 입금 확인 후 체크하는 관리자 페이지로 구성됩니다.

- **공개 현황판(공유용)**: https://cgn210-alt.github.io/jjr-sarabat2026/sarabat.html
- **관리자**: https://cgn210-alt.github.io/jjr-sarabat2026/sarabat-admin.html

## 파일 구성

- `sarabat.html` — 공개 현황판. 3개 다락방(믿음/소망/사랑) · 34개 순의 입금 여부를 실시간 표시.
- `ssalnanum2026.html` — `sarabat.html`과 내용 동일. 카카오톡 링크 미리보기 캐시가 예전 썸네일에 고정되는 문제로 만든 대체 공유 주소.
- `sarabat-admin.html` — 관리자 페이지. 로그인 후 순별로 입금완료 여부를 클릭 한 번으로 토글, 공개 현황판에 즉시 반영.
- `sarabat-og.png` / `sarabat-og-source.html` — 링크 공유 시 뜨는 썸네일 이미지와 그 제작 소스(HTML). 썸네일을 다시 만들 때 `sarabat-og-source.html`을 수정한 뒤 브라우저로 캡처해서 `sarabat-og.png`를 갱신합니다.

## 백엔드

Firebase Realtime Database (`cgn-love` 프로젝트, `sarabat2026` 경로) 사용. 관리자 로그인은 Firebase Authentication(이메일/비밀번호) — [jjr-baecharyo](https://github.com/cgn210-alt/jjr-baecharyo)의 관리자 계정과 동일한 Firebase 프로젝트를 공유합니다.

34개 순의 다락방/순번/순장 명단은 `sarabat.html`, `sarabat-admin.html` 안에 각각 직접 입력되어 있습니다 (직분은 표기하지 않고 이름만 표시).

## 배포

`사이트-올리기.bat` 더블클릭 → `git add / commit / push` 자동 실행 → GitHub Actions가 1~2분 내 자동 배포.

카카오톡 공유 썸네일이 갱신되지 않을 때는 [카카오 공유 디버거](https://developers.kakao.com/tool/debugger/sharing)에서 주소를 입력하고 캐시를 초기화하세요.
