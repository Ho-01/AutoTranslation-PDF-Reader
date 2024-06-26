# AutoTranslation-PDF-Reader
Auto translates your pdf file while reading and dragging texts. works on web browser, using PDF.js


# 사용자 가이드
자동 번역 기능이 추가된 PDF.js Viewer 사용 방법을 설명합니다.

## 주요 기능
1. 번역 툴바
- 번역 툴바 보이기/숨기기 : 상단 툴바에서 "Translate" 버튼을 클릭하여 번역 툴바를 켜거나 끌 수 있습니다.
- 번역할 텍스트 선택 : 번역하려는 텍스트를 클릭하고 드래그하여 강조 표시합니다. 선택한 텍스트는 자동으로 번역 툴바에 나타납니다.

2. 언어 감지
- 뷰어는 선택한 텍스트의 언어를 자동으로 감지하고 브라우저의 기본 언어로 번역합니다.
- 감지된 언어가 브라우저의 언어와 같으면 번역이 수행되지 않습니다.

3. 수동 언어 선택
- 번역 툴바의 드롭다운 메뉴를 사용하여 자동으로 감지된 언어가 잘못된 경우 또는 다른 대상 언어로 번역을 원할 경우 수동으로 선택할 수 있습니다.

4. API
- 번역 기능은 Google Cloud Translation API를 사용하여 정확한 번역을 제공합니다. 번역이 작동하려면 인터넷 연결이 필요합니다.

## 추가 설정
- 툴바 사용자 정의 : 사용자는 'viewer.css' 파일에서 CSS 속성을 수정하여 툴바 레이아웃을 사용자 정의할 수 있습니다.
- 번역 API 키 : API 키를 변경하려면 'translate.js' 파일의 'API_KEY' 변수를 업데이트합니다.

## 문제 해결
- 번역이 작동하지 않음 : 인터넷 연결을 확인하고 Google Cloud Translation API 키가 유효한지 확인합니다.
- 툴바가 보이지 않음 : 상단 툴바의 "Translate" 버튼을 눌러 번역 툴바가 숨겨져 있지 않은지 확인합니다.

  
# 개발자 가이드

## 시스템 요구 사항
- 하드웨어 : 표준 웹 서버 및 로컬 개발 환경
- 소프트웨어
  프론트엔드 : HTML, CSS, JavaScript, PDF.js
  백엔드 : Node.js, Express.js
  API : Google Cloud Translation API

## 구현 내용
1. 번역 툴바
- 'viewer.html' 파일 내에 번역 툴바를 위한 <div> 요소를 추가합니다.
- 'viewer.css' 파일을 사용하여 뷰어 내에서 적절한 위치에 툴바를 스타일링합니다.

2. JavaScript 로직
- 번역 관련 기능을 처리하기 위해 'translate.js' 파일을 생성합니다.
- 텍스트 선택 및 버튼 클릭 이벤트 리스너를 추가하여 번역 툴바의 가시성을 토글합니다.
- 'navigator.language' 속성을 사용하여 브라우저의 언어 설정을 감지합니다.

3. API 통합
- Google Cloud Translation API에서 API 키를 얻습니다.
- 선택한 텍스트를 API에 보내고 번역된 텍스트를 툴바에 표시하는 번역 함수를 구현합니다.

4. 언어 감지
- 선택한 텍스트의 언어를 식별하기 위해 API의 'detectLanguage' 기능을 사용합니다.
- 툴바를 수정하여 감지된 언어를 표시하고 사용자가 수동으로 대상 언어를 선택할 수 있도록 합니다.

## 테스트 및 배포
- 테스트 : 다양한 PDF 문서를 로드하여 모든 기능이 예상대로 작동하는지 확인합니다.
- 배포 : 웹 서버에 뷰어를 배포하고 환경 변수 및 API 키가 올바르게 설정되어 있는지 확인합니다.

