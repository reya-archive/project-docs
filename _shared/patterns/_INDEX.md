# _shared/patterns/_INDEX.md

**재사용 패턴 / 템플릿 모음**

여러 프로젝트에서 공통으로 사용할 템플릿, CLAUDE.md 조각, 체크리스트.

## 📋 패턴 목록

| 이름 | 파일 | 용도 |
|---|---|---|
| ADR 템플릿 | `adr-template.md` | 의사결정 기록 양식 |
| 회의록 템플릿 | `meeting-template.md` | 회의록 표준 양식 |
| 요구사항정의서 템플릿 | `spec-template.md` | 요구사항 문서 뼈대 |
| CLAUDE.md 공통 규칙 | `claude-common-rules.md` | 모든 프로젝트 공통 지침 |
| Kickoff 체크리스트 | `kickoff-checklist.md` | 프로젝트 시작 시 확인사항 |

> 필요에 따라 추가. 위는 예시.

## 🎯 활용 방법

### 패턴 참조

각 프로젝트의 CLAUDE.md 에서 import 스타일로 참조 (Claude Code 기준):

```markdown
@../../../_shared/patterns/claude-common-rules.md
```

### 템플릿 복사

새 문서 작성 시 템플릿 파일 복사:

```bash
cp ../../../_shared/patterns/adr-template.md docs/decisions/003_{주제}.md
```

## 📝 신규 패턴 등록 기준

- **최소 2개 프로젝트**에서 사용 실적이 있을 때 여기로 승격
- 특정 프로젝트 전용은 해당 프로젝트 내부에 유지
- 등록 시 이 인덱스에 행 추가 필수
