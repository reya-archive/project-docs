# _template

신규 SI 프로젝트 시작 시 복사해서 사용할 **표준 뼈대**.

## 📋 사용법

```bash
# 저장소 루트에서
cp -r _template/skeleton projects/<프로젝트명>
cd projects/<프로젝트명>
```

## ✅ 복사 후 수정해야 할 파일 체크리스트

- [ ] `README.md` — 프로젝트 메타정보 (고객사, 기간, 담당자) 채우기
- [ ] `_MANIFEST.md` — Tier 1 파일 목록 확정
- [ ] `CLAUDE.md` — 프로젝트 고유 용어, 행동 지침 보강
- [ ] `PICKUP.md` — 초기 상태로 리셋
- [ ] `docs/_MANIFEST.md` — 실제 생성할 서브폴더 기준으로 정리
- [ ] 각 `docs/*/_INDEX.md` — 초기 상태로 리셋 또는 필요 없는 폴더 삭제

## 🗂️ 폴더별 용도

| 폴더 | 용도 | Tier |
|---|---|---|
| `docs/specs/` | 요구사항정의서, 기획서, 아키텍처 설계서 | 1 |
| `docs/meetings/` | 회의록 (날짜순 누적) | 2 |
| `docs/decisions/` | 주요 의사결정 로그 (ADR 형식) | 1 |
| `docs/references/` | 외부 참조 자료, 벤치마크 | 2 |
| `docs/archive/` | 구버전, 폐기된 안 | 3 |

## 🎯 Tier 분류 원칙

- **Tier 1 (Canonical)**: Claude가 **반드시 먼저 읽을** source of truth. 요구사항·아키텍처·핵심 의사결정 등.
- **Tier 2 (Domain)**: 해당 주제 질의 시에만 로드. 회의록, 외부 참조 등.
- **Tier 3 (Archival)**: **명시 요청 시에만** 읽음. 구버전, 대체된 안.

`_MANIFEST.md`에서 각 파일이 어느 Tier인지 명시해야 Claude가 효율적으로 탐색합니다.
