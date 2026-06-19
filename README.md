<div align="center">

# 로동 공유 모듈 플랫폼
### LODONG Shared Module Platform

![Founded](https://img.shields.io/badge/Founded-2015-6f42c1?style=flat-square)
![Java](https://img.shields.io/badge/Java-21-orange?style=flat-square)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-4-6db33f?style=flat-square)
![License](https://img.shields.io/badge/license-commercial-blue?style=flat-square)

**소수의 팀이 다수의 실서비스를 안정적으로 운영하는 비결 — 검증된 공유 모듈 생태계.**

*A production-proven, versioned library platform behind multiple live services.*

[🌐 lodong.co.kr](https://lodong.co.kr) · [🏠 lodong-co](https://github.com/lodong-co) · ✉️ cyj@lodong.co.kr

</div>

---

(주)로동은 2015년 창업 이래 10년 이상 축적한 운영 경험을 바탕으로, 인증·결제·실시간 채팅 등 **반복되는 핵심 기능을 재사용 가능한 모듈로 표준화**했습니다. 이 모듈들은 사주J·Provio·forme 등 **실제 운영 중인 서비스에서 라이브로 검증**되고 있습니다.

> 본 문서는 **모듈의 기능·역할을 소개**합니다. 모듈 소스 코드와 상세 API는 공개하지 않으며, 구독 계약 시 난독화 바이너리와 함께 제공됩니다.

---

## 왜 모듈형인가

매 프로젝트를 0부터 만들지 않습니다. 인증·결제·채팅 같은 검증된 토대를 **한 번 제대로 만들어 여러 서비스에 재사용**함으로써:

- **속도** — 신규 서비스를 더 빠르게 출시
- **안정성** — 실서비스에서 검증된 코드를 재사용
- **일관성** — 서비스 전반의 보안·품질 표준 통일

> 인원이 적은 것이 약점이 아니라, **모듈 레버리지로 1인당 생산성을 높이는** 구조입니다.

---

## 모듈 카탈로그

**20여 개의 백엔드 공유 모듈**과 **모바일·데스크톱 모듈**을 독립 버전으로 관리·배포합니다. 인증·결제부터 실시간·커머스·콘텐츠·문서처리까지 서비스 구축에 반복되는 기능 대부분을 모듈로 표준화했으며, 플랫폼은 **지속적으로 확장 중**입니다.

### 핵심 모듈 (Featured)

실서비스에서 검증된 대표 모듈입니다.

| 모듈 | 역할 | 실운영 |
|---|---|---|
| [ld-chat-module](modules/ld-chat-module.md) | STOMP 실시간 채팅 (E2EE, 채널 권한) | 사주J · Provio |
| [payment-module](modules/payment-module.md) | 결제 (KCP·토스·웰컴 PG 통합) | 사주J · forme |
| [ld-jwt-member-module](modules/ld-jwt-member-module.md) | 회원 인증 (JWT, 일반·소셜·연동) | 다수 서비스 |
| [ld-utils-module](modules/ld-utils-module.md) | 공통 응답·예외처리·암호화·라이선스 게이트 | 전 서비스 공통 |
| [ld-membership-module](modules/ld-membership-module.md) | 멤버십·등급 관리 | — |
| [ld-order-module](modules/ld-order-module.md) | 주문 워크플로 | — |
| [ld-message-module](modules/ld-message-module.md) | 쪽지·메시지 (암호화) | — |
| [ld-verification-module](modules/ld-verification-module.md) | 상태머신 기반 검증 플로우 | — |

### 전체 모듈 (Full Catalog)

도메인별 전체 모듈입니다.

**🔐 인증 · 회원**
`ld-jwt-member-module` 회원 인증(일반·소셜·연동) · `ld-membership-module` 멤버십·등급

**💳 결제 · 커머스**
`payment-module` PG 결제 통합 · `submerchant-module` 하위상점(서브몰) 등록 · `ld-order-module` 주문 · `ld-product-module` 상품 · `ld-cart-module` 장바구니 · `ld-category-module` 카테고리

**⚡ 실시간 · 알림**
`ld-chat-module` 실시간 채팅(E2EE) · `ld-message-module` 쪽지·메시지 · `ld-notification-module` 알림 · `ld-push-module` 푸시

**📋 콘텐츠 · 운영**
`ld-board-module` 게시판 · `ld-comment-module` 댓글 · `ld-notice-module` 공지 · `ld-faq-module` FAQ · `ld-inquiry-module` 문의 · `ld-feedback-module` 피드백

**📄 문서 · AI**
`ld-ocr-module` OCR 문서 인식

**🧰 공통 · 인프라**
`ld-utils-module` 공통 응답·예외·암호화·라이선스 게이트 · `ld-file-module` 파일 관리 · `ld-verification-module` 상태머신 검증

> 각 모듈은 독립 버전으로 관리·배포되며, 난독화 바이너리 + 라이선스로 제공됩니다.

## 🔜 확장 중 (In Development)

백엔드 모듈을 넘어 **멀티 플랫폼**으로 확장하고 있습니다.

- **모바일 모듈** — Android · iOS WebView 셸 (웹 서비스를 네이티브 앱으로 패키징)
- **데스크톱 모듈** — 데스크톱 응용 공통 컴포넌트 (Electron · C#/.NET)
- **신규 도메인 모듈** — 지속적으로 개발·편입 중

---

## 설계 원칙 (Engineering Principles)

로동 모듈은 공통 설계 DNA를 따릅니다:

- **엔티티 비소유 패턴** — 모듈이 비즈니스 로직을 수행하되, 회원·주문 같은 핵심 엔티티의 소유권은 **호스트 앱이 갖습니다.** 공유 라이브러리가 호스트 앱의 데이터 모델을 침범하지 않는 가장 어려운 문제를 해결합니다.
- **확장 지점 우선** — 자동 설정(auto-configuration) + 조건부 빈으로, 호스트 앱이 필요한 부분만 재정의.
- **보안 우선(fail-fast)** — 키·인증서 등 필수 비밀이 없으면 **조용히 넘어가지 않고 기동을 중단**합니다.
- **검증된 경로는 테스트로 증명** — 인증·결제·금액·상태전이·암호화 등 핵심 경로는 테스트로 검증.

## 📂 케이스 스터디 (Case Studies)

서로 다른 도메인의 실제 구축 사례 — 웹부터 **IoT · 하드웨어 · 클라우드 · AI**까지.

| 사례 | 도메인 | 핵심 |
|---|---|---|
| [HRDLMS](case-studies/hrdlms.md) | 교육 · 고가용성 | 5만+ 동시접속 무중단 (네트워크·서버 이중화 + 로드밸런싱) |
| [크래쉬인 무인매장](case-studies/crashin-unmanned-store.md) | IoT · 무인매장 | 예약·결제·도어락·키오스크 통합, 오프라인 내성 |
| [강촌 포토키오스크](case-studies/gangchon-photo-kiosk.md) | 하드웨어 | 전문 포토프린터 제어 + 결제 (무인 인화) |
| [에그호스팅](case-studies/egg-hosting-platform.md) | 클라우드 인프라 | Rust 에이전트 기반 자체 호스팅 컨트롤 플레인 |
| [사주J](case-studies/sajuj-ai-saju.md) | AI · 자체제품 | 결정론 엔진 + LLM 하이브리드, 실시간·결제 |

---

## ✅ 검증된 품질 (Engineering Quality)

| | |
|---|---|
| 🏭 **실서비스 검증** | 사주J · Provio · forme 등 라이브 서비스에서 운영 중 |
| 🧪 **핵심 경로 테스트** | 결제 서명 · 인증 · 상태 전이 · 암호화 등 위험 경로 검증 |
| 🔒 **보안 우선** | fail-fast 비밀 처리 · CI 비밀 스캔 · 종단간 암호화 |
| 📦 **상용 배포 체계** | 독립 버전 관리 · 난독화 바이너리 · 라이선스 게이트 |
| 🏗 **고가용성 설계** | 5만+ 동시접속 무중단 운영 ([HRDLMS](case-studies/hrdlms.md)) |
| 🕙 **10년+ 업력** | 2015년 창업 이래 다수 서비스 구축 · 운영 |

---

## 도입 (Access)

모듈은 **구독형 상용 라이브러리**입니다.

1. 계약 → 구독 등록
2. 비공개 아티팩트 저장소(Nexus) 접근 토큰 + 라이선스 발급
3. 빌드 설정에 의존성 추가 후 사용

```gradle
// 예시 (좌표 형식). 실제 저장소 접근·버전은 계약 시 안내됩니다.
implementation "com.lodong:ld-chat-module"
```

문의: **cyj@lodong.co.kr** · https://lodong.co.kr
