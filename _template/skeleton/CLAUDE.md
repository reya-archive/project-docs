# CLAUDE.md

Claude가 이 프로젝트에서 작업할 때 따라야 할 행동 지침.

<project_context>
- 고객사: {고객사명}
- 시스템: {시스템명}
- 역할: {본인 역할}
- 민감도: NDA 대상 문서 다수 포함
</project_context>

## 🗺️ 탐색 우선순위

<navigation_priority>
작업 시작 시 반드시 이 순서로 컨텍스트 로드:

1. `_MANIFEST.md` 를 먼저 읽어 전체 파일 맵 파악
2. `_MANIFEST.md` 에서 Tier 1 으로 표시된 파일들을 먼저 읽기
3. 사용자 질의 주제와 관련된 Tier 2 파일만 선별적으로 읽기
4. **Tier 3 (archive/) 는 사용자가 명시적으로 요청할 때만 읽기**

즉시 `docs/` 하위 전체를 스캔하지 말 것. 토큰 비용과 응답 품질 모두 떨어짐.
</navigation_priority>

## 📝 응답 스타일

<response_style>
- **개념 우선**: 코드/예제 없이 개념과 원리 먼저 설명
- 사용자가 "예제", "코드" 명시적으로 요청할 때만 코드 제공
- 아키텍처 질문 → 텍스트 플로우차트 → Mermaid 순서로 시각화
- 아티팩트 자동 생성 금지. 명시적 확인 후 생성
- 토큰 효율: 핵심 정보만, 부연 최소화
</response_style>

## 🔤 용어 사용 규칙

<terminology>
- 고객사 내부 용어는 `docs/references/glossary.md` 또는 `_shared/glossary/` 참조
- 일반 용어와 고객사 용어가 충돌하면 **고객사 용어 우선**
- 영문 약어는 최초 등장 시 풀이 병기 (예: "ERP (Enterprise Resource Planning)")
- 환경 구분은 통일: 개발환경 → 검증환경 → 운영환경 (DEV/STG/PRD)
</terminology>

## 📄 문서 작성 규칙

<document_conventions>
- 새 문서 생성 시 파일명: `YYYYMMDD_문서유형_주제_v버전.md`
- 회의록: `docs/meetings/` 에 저장
- 의사결정 기록: `docs/decisions/` 에 ADR (Architecture Decision Record) 형식
- 마크다운 사용, 표·Mermaid 적극 활용
- 200줄 초과 시 서브파일로 분리
</document_conventions>

## 🔐 민감 정보 취급

<security_rules>
CRITICAL: 이 프로젝트는 NDA 대상 문서를 다룸.

다음은 **절대 외부로 전송하거나 파일에 남기지 말 것**:
- 고객사 실명 (폴더 외부 공유용 문서에서는 약칭 사용)
- 개인정보 (주민번호, 전화번호, 이메일, 실명)
- 인증 정보 (비밀번호, API 키, 토큰)
- 계약 금액, 단가 정보
- 경쟁사 관련 민감 판단

외부 공유가 필요하다면 마스킹된 사본을 별도 생성.
</security_rules>

## 🎯 작업 시 참고할 공통 자산

<shared_assets>
- `../../_shared/glossary/` — 공통 용어집 (범용 SI 용어)
- `../../_shared/patterns/` — 재사용 가능한 문서 템플릿, 체크리스트
</shared_assets>

## 🔄 세션 종료 시

<session_handoff>
중요한 작업을 마친 후에는 `PICKUP.md` 를 업데이트:
- 오늘 작업한 내용
- 다음 세션에서 이어서 할 일
- 미해결 이슈 / 대기 중인 결정
</session_handoff>
