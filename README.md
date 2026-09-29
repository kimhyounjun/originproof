# OriginProof

> Don't detect the fake. Verify the real.

결제 알림과 증빙의 진위·무결성을 서명과 검증 규칙으로 확인하는 OriginProof 프로젝트의 포트폴리오 허브입니다.

## 김형준 담당 역할

### Backend / Integration Support · M1

API, Verification, 공통 Core, 통합 지원을 담당했습니다.

- FastAPI 검증 API 및 안정적인 오류 응답
- Signed Proof 저장·조회와 DB migration
- canonical payload hash·서명·binding·replay 검증 Core
- issuer/key 신뢰 상태와 Proof lifecycle 검사
- Blockchain Reader·Analyzer 포트 통합
- HTTP E2E·smoke 테스트와 데모 실행 흐름 정리

## 핵심 검증 결과

| 케이스 | 결과 |
|---|---|
| 정상 카드 결제 알림 | `VERIFIED + ACTIVE` |
| 금액 변조 알림 | `TAMPERED + AMOUNT_MISMATCH` |
| 미등록 자료 | `NOT_REGISTERED` |

AI는 후보 필드만 추출하고 최종 진위 판정은 하지 않습니다. 최종 결과는 서명·해시·발행자·키·핵심 필드 비교를 수행하는 Verification Core에서 결정됩니다.

## 저장소

### [OriginProof Demo · M1 Backend](https://github.com/kimhyounjun/originproof-demo)

원본 모노레포에서 M1 담당 범위인 API, Verification Core, 공통 스키마, 테스트·통합 스크립트를 분리해 정리한 코드 저장소입니다.

## 기술 스택

`FastAPI` `Pydantic` `SQLAlchemy 2` `Alembic` `PostgreSQL` `Pytest` `Python` `JSON Schema`

## 원본 프로젝트

[OriginProof-3web/originproof-demo](https://github.com/OriginProof-3web/originproof-demo)
