# docs/_MANIFEST.md

`docs/` 폴더 상세 맵. 루트 `_MANIFEST.md` 를 읽은 후 참조.

## 📂 서브폴더별 용도와 Tier

### `specs/` — Tier 1
요구사항정의서, 기획서, 아키텍처 설계서 등 **Canonical 문서**.

→ 상세: `specs/_INDEX.md`

**네이밍**: `YYYYMMDD_문서유형_주제_v버전.md`
예: `20260415_요구사항정의서_v2.md`, `20260420_아키텍처설계서_v1.md`

### `meetings/` — Tier 2
주간/월간 회의, 고객사 미팅 회의록. 시간순 누적.

→ 상세: `meetings/_INDEX.md`

**네이밍**: `YYYYMMDD_회의체명_주제.md`
예: `20260415_주간회의_요구사항검토.md`

### `decisions/` — Tier 1
주요 의사결정 로그 (ADR, Architecture Decision Record).

→ 상세: `decisions/_INDEX.md`

**네이밍**: `{순번}_{주제}.md`
예: `001_인증방식선택.md`, `002_DB선정.md`

### `references/` — Tier 2
외부 참조 자료, 벤치마크, 경쟁사/유사 시스템 조사 자료.

→ 상세: `references/_INDEX.md`

### `archive/` — Tier 3
구버전, 대체된 안, 폐기된 제안.

→ 상세: `archive/_README.md`

**⚠️ Claude는 사용자 명시 요청 시에만 이 폴더를 읽음.**

## 🔍 탐색 전략

### 사용자 질의 유형별 우선 탐색 폴더

| 질의 패턴 | 우선 탐색 |
|---|---|
| "요구사항이 뭐였지?", "스펙 확인" | `specs/` |
| "지난주 회의에서", "O월 논의" | `meetings/` |
| "왜 X를 선택했지?" | `decisions/` |
| "다른 회사는 어떻게?" | `references/` |
| "이전 버전", "폐기된" | `archive/` (명시 필요) |

### 읽기 최적화

- 각 서브폴더의 `_INDEX.md` 를 먼저 읽어 **메타데이터**로 관련성 판단
- 실제 상세 파일은 필요한 것만 선별적으로 열기
- 한 세션에 많은 파일을 동시에 읽지 말 것 (토큰 낭비)
