---
type: post
title: "AngularJS commit message conventions"
---

1. feat (새로운 기능)
  설명: 새로운 기능이나 기능적 개선을 추가할 때 사용됩니다.
  예시: feat: Add payment gateway integration
2. fix (버그 수정)
  설명: 코드에서 발견된 버그를 수정할 때 사용됩니다.
  예시: fix: Correct null pointer exception in user profile
3. docs (문서 관련 변경)
  설명: 코드 외부의 문서, 예를 들어 README.md 파일이나 코드 주석을 수정할 때 사용됩니다.
  예시: docs: Update API usage instructions
4. style (코드 스타일 변경)
  설명: 코드 동작에 영향을 주지 않는 포맷팅, 세미콜론 추가/제거, 공백 수정 등의 변경에 사용됩니다.
  예시: style: Apply consistent indentation across project
5. refactor (코드 리팩토링)
  설명: 기능적인 변경 없이 코드의 구조를 개선할 때 사용됩니다.
  예시: refactor: Simplify data fetching logic
6. test (테스트 관련 코드 추가/수정)
  설명: 테스트 코드 추가, 수정 시 사용됩니다.
  예시: test: Add unit tests for user login
7. chore (기타 작업)
  설명: 빌드 프로세스 수정, 패키지 업데이트 등 개발 관련 설정 변경에 사용됩니다.
  예시: chore: Update project dependencies
8. perf (성능 개선)
  설명: 성능을 향상시키는 코드 변경에 사용됩니다.
  예시: perf: Improve image loading speed
9. build (빌드 관련 작업)
  설명: 빌드 시스템 또는 외부 종속성에 대한 변경에 사용됩니다.
  예시: build: Update build configuration for production
10. ci (CI 관련 설정 변경)
  설명: CI 설정 파일 및 스크립트 변경에 사용됩니다 (예: GitHub Actions, CircleCI).
  예시: ci: Add deployment step to GitHub Actions
11. revert (커밋 되돌리기)
  설명: 이전 커밋을 되돌릴 때 사용됩니다.
  예시: revert: Revert "feat: Add payment gateway integration"
12. BREAKING CHANGE (주요 변경 사항)
  설명: 기존 API에 호환되지 않는 변경 사항이 있을 때 사용됩니다. 커밋 메시지 본문에 명확히 기재.
  예시: feat: Remove support for old authentication method

본문에:
```

BREAKING CHANGE: Removed the old authentication method in favor of OAuth 2.0.

```

CHANGELOG.md
[참고블로그](https://velog.io/@jnary/Github-Commit-Convention)
```
git log <last tag> HEAD --pretty=format:%s
```
```
git log <last release> HEAD --grep feature
```
```
git bisect skip $(git rev-list --grep irrelevant <good place> HEAD)
```
