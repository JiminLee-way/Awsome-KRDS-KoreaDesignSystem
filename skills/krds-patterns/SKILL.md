---
name: krds-patterns
description: Use when designing page-level patterns for Korean government digital services — search flows, login, application forms, policy pages, list browsing, filtering, error handling. Triggers on 검색, 로그인, 신청, 입력폼, 목록, 필터링, 정렬, 첨부파일, 동의, 오류, 정책 정보, 서비스 패턴, 기본 패턴.
---

# KRDS 패턴 시스템

## Overview

KRDS 패턴은 기본 패턴(Global) 11종과 서비스 패턴(Service) 5종, 총 16종으로 구성됩니다.

| 구분 | 종류 | 수량 |
|------|------|------|
| 기본 패턴 (Global) | 목록 탐색, 필터링/정렬, 상세 정보, 첨부파일, 개인 식별 정보 입력, 입력폼, 동의, 도움, 사용자 피드백, 오류, 확인 | 11종 |
| 서비스 패턴 (Service) | 방문, 검색, 로그인, 신청, 정책 정보 확인 | 5종 |

## Iron Law

> 서비스 패턴의 '필수' 항목을 건너뛰지 마세요. 권장/우수는 단계적으로 확장하되, 필수는 반드시 먼저 구현하세요.

## Pattern System

### 기본 패턴 (Global Patterns)

페이지 유형에 관계없이 공통으로 적용되는 패턴입니다. 목록 탐색, 필터링/정렬, 입력폼, 첨부파일 등 어떤 서비스에서든 반복적으로 등장하는 UI 구조와 상호작용을 다룹니다.

- 참조: `references/global-patterns.md`

### 서비스 패턴 (Service Patterns)

특정 과업 흐름 전체를 다루는 패턴입니다. 사용자가 서비스에 방문하여 검색하고, 로그인하고, 신청서를 작성하고, 정책 정보를 확인하는 등 종단 간(end-to-end) 시나리오를 설계할 때 사용합니다.

- 참조: `references/service-patterns.md`

## 적용 수준

패턴의 각 가이드라인은 아래 3단계 수준으로 구분됩니다.

| 수준 | 표기 | 의미 |
|------|------|------|
| **필수** | Do | 미준수 시 사용자가 과업을 완료하지 못하거나 심각한 문제가 발생합니다. |
| **권장** | Better | 미준수 시 과업 수행 난도가 상승하고 사용자 경험이 저하됩니다. |
| **우수** | Best | 준수 시 사용자 만족도가 대폭 향상됩니다. |

## 패턴 탐색 분기

사용자 과업에 따라 아래와 같이 참조 파일을 안내합니다.

| 사용자 과업 | 참조 파일 |
|------------|----------|
| 목록을 보여주고 싶다 / 필터링·정렬이 필요하다 | `references/global-patterns.md` |
| 입력폼을 설계한다 / 첨부파일을 다룬다 | `references/global-patterns.md` |
| 동의 화면, 오류 처리, 확인 단계가 필요하다 | `references/global-patterns.md` |
| 도움말·피드백 화면을 구성한다 | `references/global-patterns.md` |
| 검색 흐름 전체를 설계한다 | `references/service-patterns.md` |
| 로그인 흐름을 설계한다 | `references/service-patterns.md` |
| 신청·접수 프로세스를 설계한다 | `references/service-patterns.md` |
| 방문(메인 화면)을 구성한다 | `references/service-patterns.md` |
| 정책 정보 페이지를 만든다 | `references/service-patterns.md` |

## 에셋 참조

패턴 구현 시 필요한 컴포넌트(버튼, 입력 필드, 페이지네이션, 배지 등)는 **krds-components** 스킬로 위임합니다. 패턴은 "무엇을, 어떤 순서로" 배치할지를 정의하고, 컴포넌트는 "어떻게 생겼고, 어떤 속성이 있는지"를 정의합니다.
