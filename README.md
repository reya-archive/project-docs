# project-docs

SI 프로젝트 문서를 **Claude Code / Cowork 에이전틱 탐색**에 최적화된 구조로 관리하는 개인 워크스페이스.

## 🎯 목적

- SI 프로젝트 문서(회의록, 기획서, 의사결정 로그 등)를 LLM이 효율적으로 탐색할 수 있는 구조로 보관
- 벡터 인덱싱이 없는 환경(Claude Code/Cowork)에서 **Tiered Manifest 패턴**으로 파일 탐색 최적화
- 신규 프로젝트 시작 시 표준화된 뼈대를 빠르게 복사·적용

## 📁 레포 구조

```
project-docs/
├── _template/       # 신규 프로젝트 시작 시 복사할 뼈대
│   └── skeleton/    # 이 폴더를 projects/ 하위로 복사해서 시작
├── projects/        # 실제 진행 중인 프로젝트들 (고객사별 폴더)
└── _shared/         # 여러 프로젝트에서 재사용하는 공통 자산
    ├── glossary/    # 공통 용어집
    └── patterns/    # 재사용 가능한 CLAUDE.md 조각, 템플릿
```

> 언더스코어 prefix(`_template`, `_shared`)는 알파벳순 정렬 시 상단 고정 목적.

## 🚀 신규 SI 프로젝트 시작하기

```bash
# 1. 템플릿 복사
cp -r _template/skeleton projects/<고객사약칭>_<시스템명>_<시작연도>

# 예시
cp -r _template/skeleton projects/HMC_차세대ERP_2026

# 2. 해당 폴더로 진입
cd projects/HMC_차세대ERP_2026

# 3. README.md, _MANIFEST.md, CLAUDE.md 를 프로젝트 컨텍스트에 맞춰 수정

# 4. Claude Code 실행 또는 Cowork에서 폴더 연결
claude
```

## 📝 네이밍 규칙

### 프로젝트 폴더
```
{고객사약칭}_{시스템명}_{시작연도}
예: HMC_차세대ERP_2026
예: LGE_MES구축_2026
```

### 파일명
```
{YYYYMMDD}_{문서유형}_{주제}_{버전}.{확장자}
예: 20260415_회의록_요구사항검토_v1.md
예: 20260420_기획서_아키텍처설계_v2.md
```

## 🔐 보안 원칙

**이 레포는 Private 운영이 전제입니다.**

- ✅ 마크다운 변환본, 요약본, 인덱스 커밋
- ❌ 고객사 원본 바이너리 파일 커밋 금지 (PPT/HWP/PDF 원본)
- ❌ 인증 정보, 개인정보, NDA 민감 데이터 커밋 금지
- 원본 파일은 사내 파일 서버에 보관, `_MANIFEST.md`에 논리 경로로만 참조

자세한 차단 규칙은 `.gitignore` 참조.

## 🤖 Claude 활용 가이드

각 프로젝트 폴더의 `CLAUDE.md`가 해당 프로젝트 전용 행동 지침.
레포 전체 공통 규칙은 `_shared/patterns/` 에서 관리.

### 탐색 우선순위 (Tiered)
- **Tier 1 (Canonical)**: 반드시 먼저 읽을 source of truth
- **Tier 2 (Domain)**: 관련 주제일 때만 로드
- **Tier 3 (Archival)**: 명시적 요청 시에만 참조 (`docs/archive/`)

## 📚 참고

- [Claude Code - How Claude remembers your project](https://code.claude.com/docs/en/memory)
- Tiered Manifest 패턴: `_template/skeleton/_MANIFEST.md` 참조
