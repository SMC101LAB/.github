
# SMC101LAB: 급경사지 데이터 시각화 프로젝트

급경사지(산사태·붕괴 위험 지역) 데이터를 체계적으로 관리하고, 현장 기술자 및 관리자가 직관적으로 위험 정보를 확인할 수 있도록 지원하는 지도 기반 위험 관리 웹·모바일 서비스

## 📋 프로젝트 개요

**SMC101LAB**은 급경사지(산사태·붕괴 위험 지역) 데이터를 중앙에서 관리하고,  
지도 기반 UI를 통해 현장 기술자와 관리자가 위험 정보를 직관적으로 확인할 수 있도록 설계된  
**웹·모바일 통합 급경사지 관리 서비스**이다.

기존 급경사지 관리 업무는 엑셀 파일과 문서 중심으로 이루어져 있어  
데이터가 여러 곳에 분산되고, 현장에서 즉시 정보를 확인하기 어려운 구조였다.  
또한 수작업으로 데이터를 수정·공유하는 과정에서 중복, 누락, 위치 오류 등의 문제가 빈번하게 발생했다.

본 프로젝트는 이러한 관리 방식을 개선하기 위해  
급경사지 정보를 하나의 시스템에서 관리하고,  
지도를 중심으로 데이터를 시각화하여 실제 현장 업무 흐름에 맞게 사용할 수 있도록 개발되었다.

---

### 서비스 구성

- **웹 애플리케이션**
  - 관리자 및 사무 환경에서 사용하는 관리용 웹 서비스
  - 급경사지 데이터 관리, 조회, 엑셀 업로드/다운로드 기능 제공

- **모바일 애플리케이션**
  - 현장 기술자를 위한 모바일 앱
  - 사용자 위치 기반 급경사지 조회 및 현장 정보 확인 가능

웹과 모바일은 동일한 백엔드 API를 사용하며,  
환경에 따라 동일한 데이터를 서로 다른 UI로 제공한다.

---

### 배포 환경

- **웹 애플리케이션**: https://smc101lab.com
- **모바일 애플리케이션**
  - iOS: App Store
  - Android: Google Play Store

실제 운영 환경을 기준으로 배포되어 있으며,  
현장 및 사무 환경에서 모두 사용 가능하도록 구성되어 있다.

---

### 개발 정보

- **개발 기간**: [기간 입력]
- **개발 인원**: 1인
- **개발 형태**: 풀스택 개발

#### 담당 역할

- 서비스 기획 및 전체 아키텍처 설계
- 웹 프론트엔드 개발 (React 기반 관리자 페이지)
- 모바일 앱 개발 (React Native 기반 현장용 앱)
- 백엔드 API 개발 및 데이터베이스 설계
- AWS S3 연동 및 배포 환경 구성
- GitHub Actions 기반 CI/CD 구축
- App Store / Google Play 배포 및 운영

## 🛠 기술 스택

### Frontend (Web)

- **Core**: React 18, TypeScript, Vite
- **UI**: Styled-components, MUI
- **State Management**: TanStack Query, Zustand
- **Table**: TanStack Table
- **Map**: react-naver-maps (네이버 지도 API)
- **Analytics**: React GA4

### Backend

- **Runtime**: Node.js, Express, TypeScript
- **Database**: MongoDB, Mongoose
- **Authentication**: JWT, Bcrypt
- **Storage**: AWS S3
- **Data Processing**: ExcelJS

### Mobile (React Native)

- **Framework**: Expo SDK ~52, React Native 0.76.7
- **WebView**: react-native-webview
- **Location**: expo-location
- **Media**: expo-image-picker, expo-file-system
- **Permissions**: react-native-permissions

### Infrastructure & Tools

- **Deployment**: AWS S3, Netlify
- **CI/CD**: GitHub Actions
- **App Distribution**: App Store, Google Play Store

---

## ✨ 주요 기능

### 1. 지도 기반 급경사지 시각화

네이버 지도 API를 활용하여 전국 급경사지 데이터를 지도 위에 시각화합니다.

- 위험 등급, 상태에 따른 마커 색상 및 스타일 차별화
- 지도 확대/축소 시에도 성능 저하 없는 렌더링 최적화
- 사용자 위치 기반 주변 급경사지 검색
- 바텀시트를 통한 상세 정보 표시

[GIF]

---

### 2. 급경사지 데이터 관리

관리자 페이지에서 급경사지 데이터를 체계적으로 관리할 수 있습니다.

- 급경사지 기본 정보, 점검 이력, 상태 데이터 CRUD
- TanStack Table을 활용한 대용량 데이터 테이블
- 필터링, 정렬, 페이지네이션 기능
- 이상값 데이터 자동 탐지 (중복, 빈 값, 위치 오류)
- 회원 관리 기능

[GIF]

---

### 3. 엑셀 업로드/다운로드

대량 데이터를 효율적으로 처리할 수 있는 엑셀 연동 기능을 제공합니다.

- **일괄 업로드**: 엑셀 파일을 통한 대량 데이터 등록
- **데이터 검증**: 업로드 시 형식 검증 및 예외 처리
- **엑셀 다운로드**: 현재 데이터를 엑셀 파일로 내보내기
- 오프라인 업무 및 보고서 작성 지원

[GIF]

---

### 5. 댓글 시스템

급경사지별 현장 정보를 공유할 수 있는 댓글 기능을 제공합니다.

- 급경사지별 댓글 작성, 수정, 삭제
- 이미지 첨부 지원 (모바일 갤러리 연동)
- AWS S3를 통한 이미지 저장 및 관리
- 현장 상황 실시간 공유

[GIF]

---
