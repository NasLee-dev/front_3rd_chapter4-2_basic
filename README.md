# Chapter 4-2. 성능 최적화 Basic

## 배포 주소

- https://dgz74mnk6or08.cloudfront.net

## 성능 개선 보고서

### 측정 도구

- PageSpeed Insights

### 성능 전후 비교

---

1. image 파일 최적화(webp 적용)

| 항목   | 성능 개선 전 지표 | 성능 개선 후 지표 |
| ------ | ----------------- | ----------------- |
| LCP    | 2.8초             | 0.7초             |
| 이미지  | <img width="1440" alt="lighthouse_total" src="https://github.com/user-attachments/assets/bf9b20db-b841-476c-b9e3-762fda2ebfea">| <img width="1440" alt="webp_overall" src="https://github.com/user-attachments/assets/950f82e3-bab4-4d4a-b8fd-8f0b3bc961ff">|
|개선사항| lazy load 미적용, alt 미적용, width / height 미적용| webp확장자 변경, lazy load 적용, width / height 적용|

2. CSS 및 font 최적화

| 항목   | 성능 개선 전 지표 | 성능 개선 후 지표 |
| ------ | ----------------- | ----------------- |
| 이미지  | <img width="1440" alt="lighthouse_total" src="https://github.com/user-attachments/assets/bf9b20db-b841-476c-b9e3-762fda2ebfea">|<img width="1440" alt="lighthouse_last_overall" src="https://github.com/user-attachments/assets/3477e7f5-e048-4b1a-848b-ac8d568ccf9b">
|개선사항 | google font link 태그 사용 | 직접 ttf 파일 삽입 후 사용|

---

### 중점 개선 사항
1. LCP(Largest Contentfull Paint)
 - 선정 이유: LCP는 사용자에게 페이지 로드 시 가장 큰 콘텐츠의 로딩 시간을 의미함. 이는 FCP와 더불어 사용자 경험에 큰 영향을 미치는 요소입니다. 따라서 해당 요소를 개선함으로써 사용자 경험의 개선을 기대할 수 있습니다.
 - 성능 개선 전 초기 LCP는 2.8초로, 일반적으로 기대하는 2.5초의 범위를 벗어난 지표였습니다. 이는 사용자 이탈율 증가 및 검색 엔진 최적화에 상당한 방해요소로 작용됩니다. 이를 0.7초로 줄임으로써 기존의 문제를 해결함은 물론, 사용자의 경험에 긍정적인 영향을 미칠 것으로 기대됩니다.

2. 이미지 최적화
 - 선정 이유: jpg 확장자는 비효율적인 확장자로 효율성에서 떨어지는 형식입니다. 따라서 이를 대체할 수 있는 webp형식을 차용함으로써 추가 성능의 개선을 기대할 수 있습니다.
 - 성능 개선 전 기존의 img 태그는 lazy loading이 적용되지 않은 상태였습니다. 이는 초기에 모든 이미지를 한 번에 로드하여 초기 렌더링 속도에 주요한 영향을 미쳤습니다. 이를 개선함으로써, 그리고 추가적으로 스크롤의 위치에 따라 이미지를 로딩함으로써 초기 렌더링 향상을 기대할 수 있습니다.

3. fonts / CSS 최적화
 - 선정 이유: google font를 직접 네트워크 요청하여 성능 저하. 사용하지 않는 CSS 코드들로 인한 성능저하
 - font 파일을 직접 폴더에 삽입을 하였고, 불필요한 코드들을 정리, 개선하여 전체적인 성능을 개선하였습니다.
