---
title: "이력서 기반 채용 인텔리전스 플랫폼"
description: "내 이력서와 경력기술서를 기준으로 채용공고 검색 조건을 만들고, 공고를 수집·정규화·분석해 검토 우선순위를 제공하는 개인 프로젝트."
pubDate: 2026-06-05
period: "2026 개인 프로젝트"
role: "제품 기획 / 백엔드·UI 구현 / AI 활용 설계"
stack:
  - FastAPI
  - SQLAlchemy
  - SQLite
  - Jinja2
  - Vanilla JavaScript
  - BeautifulSoup
  - Playwright
  - OpenAI API
summary: "채용사이트를 많이 조회하는 자동화가 아니라, 내 경력에 맞는 공고를 찾기 위한 검색 전략과 판단 기준을 시스템으로 만든 프로젝트입니다."
highlights:
  - "이력서 기반 검색어와 제외 조건 생성"
  - "사이트별 수집 결과를 표준 필드로 정규화"
  - "AI 기반 공고 요약과 기술스택 추출"
  - "프로필 적합도 점수와 추천/감점 근거 제공"
order: 4
featured: true
confidentialityNote: "수집 데이터와 실행 결과는 공개 시 샘플 또는 비식별 데이터로 대체합니다. 로그인 우회와 개인정보 수집은 범위에 포함하지 않습니다."
---

## 문제 정의

채용사이트마다 검색 조건, 필터 구조, 공고 상세 형식이 다릅니다. 수작업으로 공고를 찾으면 누락과 중복이 생기고, 내 경력과 맞지 않는 공고를 반복해서 보게 됩니다.

## 시스템 구조

```text
Candidate Profile
-> Query Planner
-> Site Collectors
-> Normalizer
-> Raw Store / DB
-> AI Enrichment
-> Profile Fit Scoring
-> Web UI / Export
```

## AI 활용 기준

AI를 최종 판단자로 사용하지 않습니다. 공고 본문에서 기술스택, 주요 업무, 요구사항을 구조화하고 요약하는 보조 계층으로 사용합니다. 최종 검토 우선순위는 내 프로필의 강점 기술, 도메인, 제외 키워드와의 매칭 근거를 함께 남기는 방식으로 설계합니다.

## 포트폴리오에서 강조할 점

이 프로젝트는 Python/FastAPI 자체보다 문제를 구조화하는 방식이 핵심입니다. 이력서에서 강점 기술과 제외 조건을 뽑고, 사이트별 필터를 표준화하고, raw 데이터와 정규화 데이터를 분리해 검토 가능한 형태로 만드는 과정을 보여줍니다.
