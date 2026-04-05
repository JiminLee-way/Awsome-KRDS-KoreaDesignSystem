---
name: krds-license
description: Use as the final step before deploying or committing any project that uses KRDS. Verifies copyright attribution, inserts required license text, and checks for proper source citations. Triggers on 배포, 커밋, 완료, 출시, 저작권, 라이선스, 공공누리, deploy, publish.
---

## Iron Law

```
NO DEPLOYMENT WITHOUT COPYRIGHT ATTRIBUTION
KRDS를 사용한 프로젝트는 저작권 표기 없이 배포/커밋하지 마세요.
```

## 자동 검증 체크리스트

이 스킬이 실행되면 자동으로 3가지를 검증합니다:

| # | 검증 항목 | 확인 방법 |
|---|----------|----------|
| 1 | 출처 표기 텍스트 존재 | Grep으로 프로젝트 전체에서 "KRDS" 또는 "범정부" 또는 "디자인시스템" 검색 |
| 2 | KRDS 홈페이지 링크 | Grep으로 "krds.go.kr" 검색 |
| 3 | 공공누리 유형 명시 | Grep으로 "공공누리" 검색 |

3개 모두 P(Pass)여야 합니다. 하나라도 F(Fail)이면 출처 표기 삽입을 제안합니다.

## 필수 출처 표기 문구

다음 문구가 프로젝트 어딘가에 반드시 존재해야 합니다:

```
본 저작물은 행정안전부에서 작성하여 공공누리 제1유형으로 개방한
'범정부 UI/UX 디자인시스템(KRDS)'을 이용하였으며,
해당 저작물은 KRDS 디자인시스템 홈페이지(www.krds.go.kr)에서
무료로 다운받으실 수 있습니다.
```

가능한 경우 www.krds.go.kr에 하이퍼링크를 제공하세요.

## 삽입 위치 분기

프로젝트 유형에 따라 출처 표기 위치가 다릅니다:

| 프로젝트 유형 | 삽입 위치 |
|-------------|----------|
| **웹사이트** | 푸터 하단 또는 별도 저작권 페이지 |
| **오픈소스 프로젝트** | README.md 하단 + LICENSE 또는 NOTICE 파일 |
| **npm 패키지** | package.json의 `license` 필드 + README |

## 공공누리 제1유형 조건 안내

KRDS의 모든 자료는 공공누리 제1유형에 따라 제공됩니다:

1. **출처 표기 필수**: 저작물의 출처를 구체적으로 표시해야 합니다
2. **상업적 이용 가능**: 상업적, 비상업적 용도 모두 자유롭게 사용 가능
3. **변경 허용**: 변경, 가공, 2차적 저작물 제작과 배포 허용

단, 잘못된 방식으로 변형된 공공저작물 이용으로 발생하는 손해나 불이익에 대해서는 책임지지 않습니다.

자세한 정보: https://www.kogl.or.kr/

## 미준수 시 동작

검증 결과 출처 표기가 누락된 경우:

1. 사용자에게 알림: "KRDS 출처 표기가 누락되었습니다."
2. 삽입 제안: "출처 표기를 추가하시겠습니까?"
3. **승인 시**: 적절한 위치(README 하단 또는 LICENSE 파일)에 필수 문구 자동 삽입
4. **거부 시**: 경고 메시지 출력 후 종료. 배포를 차단하지는 않지만, 출처 표기 의무를 명확히 안내

## Red Flags

다음 상황이면 이 스킬을 반드시 실행하세요:
- `git push` 전
- 배포 스크립트 실행 전
- npm publish 전
- PR 생성 전
- "완료", "다 됐어", "배포해줘" 등의 발화 시

## Integration

- **Called by**: krds-verify 완료 후 마지막 단계로 호출
- **Pairs with**: krds-onboarding (초기 설정 시에도 LICENSE 파일 생성 안내)
