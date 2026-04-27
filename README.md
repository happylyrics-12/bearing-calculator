# Bearing Life Calculator (베어링 수명 계산기)

ISO 281:2007 시스템 어프로치 기반 베어링 수명 계산기. 단일 HTML 파일, 백엔드 불필요, 모든 계산은 브라우저에서 수행됩니다.

🇰🇷 [한국어](./index.html) | 🇬🇧 [English](./en/index.html)

## 주요 기능

- **베어링 6종 지원**: 깊은홈 볼, 원통 롤러(NU/NJ/NUP/NJF), 테이퍼 롤러, 자동조심, 앵귤러 컨택트, 스러스트
- **제조사 4종 데이터셋**: ISO 표준 / SKF / NSK / FAG (X·Y·e 계수 차이 반영)
- **다중 하중 스펙트럼**: 운전 사이클 합성 (회전수 가중 등가하중)
- **Expert Mode**: a₁ / a₂ / a₃ / X / Y / e 수동 오버라이드
- **단위계 토글**: SI ↔ Imperial (자동 변환)
- **2가지 계산 모드**:
  - ISO 281:1990 + DIN 626 확장 (a₁·a₂·a_ISO) — 기본
  - ISO 281:2007 Strict (a₁·a_ISO, a₂=1)
- **자동 추정**: Pᵤ 값 (베어링 종류·내경 크기별 24-셀 테이블)
- **분석 항목**:
  - L₁₀ / L₁₀ₘ 수명, 동·정적 안전계수
  - 마찰 토크 (Palmgren 형식)
  - 최소하중·재급유 주기 (SKF 공식)
  - 점도비 κ, 윤활 상태, 클리어런스/정밀도 등급 영향
- **출력**: CSV 내보내기, PDF 보고서 (html2canvas), 차트 4종 (Chart.js)
- **저장**: localStorage 기반 계산 결과 보존/불러오기 (최대 50건)
- **그리스 윤활**: 베이스오일 점도, 증주제 종류 별도 입력

## 적용 표준

- ISO 281:2007 (시스템 어프로치, 근사식 구현)
- ISO/TS 16281 (윤활 보정 일부)
- DIN 626 (온도·재료 확장)
- ISO 4406 (오염도 등급), ISO 492 (정밀도 등급)
- SKF General Catalogue (마찰·재급유)

## 한계 (정직 표기)

- a_ISO는 ISO 281:2007 차트의 **근사식** (정밀 디지타이징 대비 ±15% 가능)
- ISO/TS 16281 풀버전(롤러 슬라이스별 응력 분포, 케이지·롤러 슬립 동역학)은 범위 밖
- 임계 설계는 반드시 제조사 도구(SKF SimPro, MESYS, Romax) 또는 시험 데이터로 검증 권장

## 로컬 실행

```bash
# 그냥 브라우저에서 index.html 열기
open index.html

# 또는 간단한 정적 서버
python3 -m http.server 8000
# http://localhost:8000 접속
```

## 배포 (Vercel)

`vercel.json` 등 별도 설정 없이 정적 파일 자동 인식. GitHub repo를 Vercel에 연결하면 main 푸시 시 자동 재배포.

## 외부 의존성 (CDN)

모두 브라우저에서 자동 로드:
- [jsPDF 2.5.1](https://cdnjs.com/libraries/jspdf) — PDF 생성
- [html2canvas 1.4.1](https://cdnjs.com/libraries/html2canvas) — 결과 영역 캡처 (한글 PDF 렌더링)
- [Chart.js](https://cdn.jsdelivr.net/npm/chart.js) — 차트 4종

## 라이선스 / 저작권

© 2025 Tool-Play | Professional Engineering Tools
