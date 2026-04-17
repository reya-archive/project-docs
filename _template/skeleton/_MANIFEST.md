# _MANIFEST.md

이 프로젝트의 전체 파일 맵. **Claude는 작업 시작 시 이 파일을 먼저 읽어야 함.**

## 📂 구조 개요

```
{프로젝트명}/
├── README.md              [메타]   프로젝트 개요
├── CLAUDE.md              [지침]   Claude 행동 규칙
├── _MANIFEST.md           [맵]     지금 이 파일
├── PICKUP.md              [상태]   마지막 세션 요약
└── docs/                  [콘텐츠] 실제 문서들
    └── _MANIFEST.md       [맵]     docs 하위 상세 맵
```

## 🎯 Tier 분류

### Tier 1 — Canonical (반드시 먼저 읽기)

이 프로젝트의 source of truth. 다른 문서와 충돌 시 Tier 1 우선.

| 파일 | 설명 |
|---|---|
| `README.md` | 프로젝트 메타정보, 네비게이션 |
| `CLAUDE.md` | Claude 행동 지침 |
| `docs/specs/요구사항정의서_최신.md` | {최신 요구사항} — 실제 파일명으로 교체 |
| `docs/specs/아키텍처설계서_최신.md` | {최신 아키텍처} — 실제 파일명으로 교체 |
| `docs/decisions/_INDEX.md` | 주요 의사결정 타임라인 |

### Tier 2 — Domain (관련 주제일 때만 로드)

특정 질의 주제와 관련된 경우에만 선별적으로 읽기.

| 영역 | 경로 | 언제 읽나 |
|---|---|---|
| 회의록 | `docs/meetings/` | "지난 회의에서", "O월 논의" 등 시점 질의 |
| 외부 참조 | `docs/references/` | 벤치마크, 외부 표준 질의 |

### Tier 3 — Archival (명시 요청 시에만)

| 경로 | 내용 |
|---|---|
| `docs/archive/` | 구버전, 대체된 안, 폐기된 제안 |

**사용자가 "이전 버전", "폐기된", "archive" 등을 명시할 때만 읽을 것.**

## 📌 현재 Canonical 파일 목록 (최신성 보증)

> 이 섹션은 프로젝트 진행하며 지속적으로 업데이트 필수.

- 요구사항: `docs/specs/{파일명}` (최종 수정: YYYY-MM-DD)
- 아키텍처: `docs/specs/{파일명}` (최종 수정: YYYY-MM-DD)
- 핵심 일정: `docs/specs/{파일명}` (최종 수정: YYYY-MM-DD)

## ⚠️ Deprecated (읽지 말 것)

구버전이지만 아직 삭제하지 않은 파일들. Claude는 이 목록의 파일을 참조하지 않음.

- (없음 — 프로젝트 진행하며 추가)

## 🔗 외부 원본 위치

GitHub 레포에는 변환본/요약본만 존재. 원본은 사내 파일 서버에:

```
원본 위치: {사내 파일 서버 경로}
예: \\fileserver\projects\{고객사}\{프로젝트}\
```

---

**업데이트 주기**: 매주 월요일 또는 주요 문서 추가/변경 시
**마지막 업데이트**: {YYYY-MM-DD}
