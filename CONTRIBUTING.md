# CostFlow 기여 가이드

이 문서는 CostFlow 저장소의 Git 작업 규칙을 정의합니다. 기능 개발, 문서 작성, 버그 수정 등 모든 변경에 동일하게 적용합니다.

## 핵심 원칙

- `main` 브랜치에 직접 커밋하지 않습니다.
- 모든 작업은 GitHub Issue를 먼저 생성한 뒤 시작합니다.
- 하나의 브랜치는 하나의 Issue를 처리하는 것을 원칙으로 합니다.
- 모든 변경은 Pull Request(PR)를 통해 검토한 뒤 `main`에 병합합니다.

> 저장소 최초 초기화를 위해 생성한 `main`의 첫 README 커밋은 PR 기준 브랜치를 만들기 위한 1회성 예외입니다.

## 작업 흐름

모든 작업은 다음 순서로 진행합니다.

1. **GitHub Issue 생성**
   - 작업의 목적, 범위, 완료 조건을 작성합니다.
2. **Issue 번호 기반 브랜치 생성**
   - 작업 유형과 Issue 번호, 간단한 설명을 브랜치명에 포함합니다.
3. **변경 작업 및 Commit**
   - 변경 목적이 드러나는 커밋 메시지를 작성하고 Issue 번호를 연결합니다.
4. **Pull Request 생성**
   - `main` 브랜치를 대상으로 PR을 생성합니다.
5. **Review / Check**
   - 변경 내용을 검토하고 필요한 자동 검사를 통과했는지 확인합니다.
6. **Main Merge**
   - 검토가 끝난 PR만 `main`에 병합합니다.
7. **Issue Close**
   - 병합 후 연결된 Issue가 종료되었는지 확인합니다.

`Issue → Branch → Commit → PR → Review/Check → Main Merge → Issue Close`

## 브랜치 이름

다음 형식을 사용합니다.

`<type>/<issue-number>-<short-description>`

예시:

```text
docs/1-project-overview
feat/10-cost-calculation
fix/24-margin-calculation
```

주요 유형:

- `docs`: 문서 작성 또는 수정
- `feat`: 기능 추가
- `fix`: 버그 수정
- `refactor`: 동작 변경 없는 코드 개선
- `test`: 테스트 추가 또는 수정
- `chore`: 설정, 도구, 기타 유지보수 작업

## 커밋 메시지

다음 형식을 사용합니다.

`<type>: <변경 요약> (#<issue-number>)`

예시:

```text
docs: 프로젝트 개요 작성 (#1)
feat: 환율 기반 원가 계산 추가 (#10)
fix: 마진 계산 오류 수정 (#24)
```

커밋은 가능한 한 하나의 목적에 집중하고, 변경 요약은 명확하고 간결하게 작성합니다.

## Pull Request

PR 제목은 Issue 번호와 작업 내용을 포함합니다.

`[#<issue-number>] <작업 내용>`

예시:

```text
[#1] 프로젝트 개요 문서 작성
```

PR 본문에는 다음 내용을 포함합니다.

- 관련 Issue
- 변경 사항
- 확인 방법
- 리뷰 시 참고 사항

가능하면 PR 본문에 `Closes #<issue-number>`를 포함하여 병합 시 Issue가 자동으로 종료되도록 합니다.

## 병합 전 확인 사항

- [ ] 연결된 Issue가 있습니다.
- [ ] 브랜치명이 규칙에 맞습니다.
- [ ] 커밋 메시지에 Issue 번호가 포함되어 있습니다.
- [ ] PR 대상 브랜치가 `main`입니다.
- [ ] 변경 내용을 직접 검토했습니다.
- [ ] 필요한 테스트 또는 문서 확인을 완료했습니다.
- [ ] 리뷰와 자동 검사가 모두 통과했습니다.
