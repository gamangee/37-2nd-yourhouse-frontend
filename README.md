![yourhouse_bar](https://user-images.githubusercontent.com/84329979/202771505-581e6d09-b074-4b64-b6c3-368f5717a526.jpg)

### 프로젝트 소개
라이프 스타일 커뮤니티의 대표적인 사이트는 오늘의집이다. 오늘의집 사이트를 모티브로 상품 태그, 해시태그, 댓글, 좋아요, 팔로우, 소셜로그인 모든 기능이 있는 **심화된 SNS 사이트를 구축**해 보았다.

<br>

### 📌 선정 이유
**사용자가 클릭한 위치에 상품을 태그**하고 이미지와 함께 글을 올릴 수 있는 기능을 개발해보고 싶어서 선택하게 되었다.
<br><br>
### 개발 인원 및 기간
`기간` : 2022/10/3 ~2022/10/14 <br>
`인원` : 프론트엔드 4명, 백엔드 3명
<br><br>
### 구현 기능
![yourhouse_mine](https://user-images.githubusercontent.com/84329979/202771445-8ee50891-cadc-49bc-8407-6e14f945b522.gif)

1. 사진 업로드
- 사용자는 `handleUploadImg` 함수를 통해 최대 10장의 사진을 업로드할 수 있습니다.
- 업로드한 사진은 `uploadedImgs` 배열에 저장됩니다. 이미 업로드된 사진이 있다면 추가로 사진을 업로드할 수 있습니다.
- 업로드한 사진은 `uploadedImgs` 배열을 map 함수를 사용하여 화면에 미리보기로 표시됩니다.

<br/>

2. 업로드된 사진에 상품 태그 기능
```javascript
   handlePosition({
      x: (
        (e.clientX - e.target.getBoundingClientRect().left) /
        imgRef.current?.offsetWidth
      ).toFixed(4),
      y: (
        (e.clientY - e.target.getBoundingClientRect().top) /
        imgRef.current?.offsetHeight
      ).toFixed(4),
    });
```
- 마커의 위치를 상대적인 좌표값으로 계산하여, 화면 크기나 요소의 크기에 관계없이 다른 페이지에서 일관성 있게 보여줄 수 있습니다.
- `react-draggable` 라이브러리를 사용하여 사용자가 마커를 드래그 할 수 있도록 합니다.
- 마커의 위치는 marker 객체로 저장되며, `handlePosition` 함수를 통해 이동한 마커의 위치 정보를 갱신합니다.
- 사용자가 사진을 클릭하고 마커를 원하는 위치로 드래그하면` handleModal` 함수가 실행됩니다. 이때, 마커의 위치가 변경되면서 `isTagged`와 `isClickedModal` 상태가 변경됩니다.
  
<br/>

3. 상품 태그 등록 시 상품 검색
- 사용자가 상품 태그를 등록하면 해당 상품과 관련된 검색 결과를 불러옵니다. 이를 위해 handleProductId 함수가 사용됩니다.
- 사용자가 상품 태그를 클릭하면 handleProductId 함수가 실행되고, 해당 상품의 정보와 검색 결과가 uploadInfo 객체의 marker와 productInfo에 저장됩니다.
- 검색된 상품 정보는 모달창에 리스트 형태로 표시되고, 사용자는 원하는 상품을 선택할 수 있습니다.

<br/>

4. 상품 태그 수정
- 등록한 상품 태그를 클릭하면 `handleProductModal` 함수가 실행되고, 상품 정보를 수정하는 모달창이 나타납니다.
- 수정된 정보는 `handlePosition`과 `handleProductId` 함수를 통해 갱신됩니다.

<br/>

5. 사진 정보 기입
- 사용자는 공간, 평수, 주거형태, 스타일에 대한 정보를 `handleInput` 함수를 통해 선택할 수 있습니다. 선택한 정보는 `uploadInfo` 객체에 저장됩니다.
- 키워드는 `TagsInput` 컴포넌트를 통해 해시태그 형식으로 입력할 수 있습니다. 사용자가 키워드를 입력하면 `handleHashtag` 함수가 실행되어 키워드가 `uploadInfo` 객체의 `hashTag` 배열에 저장됩니다.
- 자세한 부연 설명은 `handleComment` 함수를 통해 `textarea` 태그에 입력됩니다.

<br>

### 적용 기술
<div>
<img src="https://img.shields.io/badge/react-61DAFB?style=for-the-badge&logo=react&logoColor=white"> <img src="https://img.shields.io/badge/styled-components-DB7093?style=for-the-badge&logo=styled-components&logoColor=white">
</div>

<br>

### 회고
#### 
[👉 기술블로그 바로가기](https://velog.io/@gamangee/%EB%84%88%EB%84%A4%EC%A7%91-2%EC%B0%A8-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%B5%9C%EC%A2%85-%ED%9A%8C%EA%B3%A0)

<br>

## Reference

- 이 프로젝트는 [오늘의 집](https://ohou.se/)사이트를 참조하여 학습목적으로 만들었습니다.
- 실무수준의 프로젝트이지만 학습용으로 만들었기 때문에 이 코드를 활용하여 이득을 취하거나 무단 배포할 경우 법적으로 문제될 수 있습니다.
- 이 프로젝트에서 사용하고 있는 사진 대부분은 위코드에서 구매한 것이므로 해당 프로젝트 외부인이 사용할 수 없습니다.
