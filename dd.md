<!DOCTYPE html>
<html lang="en">
<head>
     <meta charset="UTF-8">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <style>
.tooltip {
    position: absolute; /* 절대 위치 설정 */
    background: rgba(255, 255, 255, 0.8); /* 툴팁 배경색 */
    color: black; /* 텍스트 색상 */
    padding: 5px; /* 여백 */
    border-radius: 5px; /* 모서리 둥글게 */
    display: none; /* 숨김 */
    z-index: 20; /* 툴팁을 다른 요소 위에 표시 */
}


     body {
         margin: 0; /* 기본 마진 제거 */
         overflow: hidden; /* 스크롤 바 숨기기 */
         height: 100vh; /* 화면 높이 100% */
         width: 100vw; /* 화면 너비 100% */
     }

     .page {
         height: 100vh; /* 각 페이지가 화면 높이를 꽉 채움 */
         width: 100vw; /* 각 페이지가 화면 너비를 꽉 채움 */
         display: flex; /* 플렉스 박스 사용 */
         justify-content: center; /* 수평 중앙 정렬 */
         align-items: center; /* 수직 중앙 정렬 */
         flex-direction: column; /* 세로 방향 정렬 */
         color: white; /* 글자 색상 */
         transition: transform 0.5s ease; /* 페이지 전환 애니메이션 */
     }

     .page:nth-child(odd) {
         background-color: #000000; /* 홀수 페이지 배경 색상 */
     }

     .page:nth-child(even) {
         background-color: #000000; /* 짝수 페이지 배경 색상 */
     }

     h1 {
         font-size: 10vw; /* 글자 크기 */
         text-align: center; /* 텍스트 중앙 정렬 */
         cursor: pointer; /* 클릭 가능하게 커서 변경 */
     }

     p {
         font-size: 20px; /* 본문 글자 크기 */
         text-align: center; /* 본문 중앙 정렬 */
         max-width: 600px; /* 최대 너비 제한 */
         padding: 20px; /* 여백 추가 */
     }

     .images {
         display: flex; /* 플렉스 박스 사용 */
         justify-content: center; /* 수평 중앙 정렬 */
         flex-wrap: wrap; /* 줄 넘김 */
         gap: 10px; /* 이미지 간격 */
     }

     .images img {
         width: 150px; /* 이미지 너비 */
         height: auto; /* 비율 유지 */
         border-radius: 10px; /* 모서리 둥글게 */
     }
     .page img {
    width: 50%; /* 로고 너비 */
    height: auto; /* 비율 유지 */
    }


     #info {
    position: absolute; /* 절대 위치 설정 */
    top: 50%; /* 상단에서 중앙 위치 */
    left: 50%; /* 좌측에서 중앙 위치 */
    width: 70%; /* 전체 너비의 80% */
    height: 80vh; /* 전체 높이의 80% */
    background: rgba(0, 0, 0, 0.8); /* 배경 반투명 */
    color: white; /* 글자 색상 */
    padding: 20px; /* 여백 */
    border-radius: 10px; /* 모서리 둥글게 */
    display: none; /* 숨김 */
    z-index: 10; /* 다른 요소 위에 표시 */
    transform: translate(-50%, -50%); /* 중앙 정렬 */
    justify-content: center; /* 수평 중앙 정렬 */
    align-items: center; /* 수직 중앙 정렬 */
    flex-direction: column; /* 세로 방향 정렬 */
}
.info-text {
    font-size: 20px; /* 본문 글자 크기 */
    text-align: center; /* 본문 중앙 정렬 */
    max-width: 100%; /* 최대 너비 제한 */
    padding: 20px; /* 여백 추가 */
    white-space: nowrap; /* 한 줄로 표시 */
    overflow: hidden; /* 넘치는 내용 숨기기 */
    text-overflow: ellipsis; /* 넘치는 내용에 '...' 표시 */
    cursor: pointer; /* 클릭 가능하게 커서 변경 */
}

     .hidden {
         display: none; /* 숨김 클래스 */
     }
     </style>
     <title>CASTLE</title>
</head>
<body>
    <div class="page" id="page1">
        <a href="https://comic.naver.com/webtoon/list?titleId=807178" target="_blank"
        title="보러가기" style="text-decoration: none; color: inherit;">
            <h1>CASTLE</h1>
        </a>
    </div>
    
     <div class="page" id="page2">
         <p>뒷세계 절대권력 '캐슬'을 무너뜨리기 위하여 
             전국의 남자들을 모아 '백의'를 조직한 특급킬러 '김신'은
             그렇게 캐슬 내부로 들어가 적과의 동침을 시작하는데.. 
             과연 김신은 자신이 염원하던대로 캐슬을 무너뜨리고 
             복수를 완성할 수 있을까.
         </p>
     </div>
    <div class="page" id="page3">
        <img src="baeguirogo.jpg" alt="백의" style="width: 50%; height: auto;" onclick="showInfo('백의', event)"> <!-- 로고 이미지 -->
    </div>
    <div class="page" id="page4">
        <img src="hasungrogo.jpg" alt="하성" style="width: 50%; height: auto;" onclick="showInfo('하성', event)"> <!-- 로고 이미지 -->
    </div>
    <div class="page" id="page5">
        <img src="huajinrogo.jpg" alt="华津" style="width: 50%; height: auto;" onclick="showInfo('화진', event)"> <!-- 로고 이미지 -->
    </div>
    <div class="page" id="page6">
        <img src="iskrarogo.jpg" alt="искра" style="width: 50%; height: auto;" onclick="showInfo('이스크라', event)"> <!-- 로고 이미지 -->
    </div>
    <div class="page" id="page7">
        <img src="castlehotelrogo.jpg" alt="HOTEL" style="width: 50%; height: auto;" onclick="showInfo('캐슬호텔', event)"> <!-- 로고 이미지 -->
    </div>
    <div class="page" id="page8">
        <img src="castleholdingsrogo.jpg" alt="HOLDINGS" style="width: 50%; height: auto;" onclick="showInfo('캐슬홀딩스', event)"> <!-- 로고 이미지 -->
    </div>
    
      <body onclick="hideInfo(event)">
        ...
        <div id="info" class="hidden">
            <h2 id="info-title"></h2>
            <p id="info-description"></p>
            <div class="images" id="info-images"></div>
        </div>
        <div class="tooltip" id="tooltip"></div>
    </body>
    
    
      

     <script>
        const characterTooltips = {
    'kimsin': '김신: 캐슬에 원한을 품은 자 아버지와 스승 강민성이 캐슬에 죽음을 당했다. 현재 무력으론 당해낼 자가 없다.',
    'saroka': '서진태: 김신의 오른팔 어린시절 김신에게 구원받았다.',
    'bolk': '피우진: 강민성의 제자중 한명',
    'gimtaehun': '김태훈: 하성의 수장 하성을 양지로 끌어올리려는 야망을 가진다',
    'ryujihak': '류지학: 하성의 칼',
    'yuuseong': '유우성: 화진의 수장 홍콩 밤거리의 패자이다.',
    'richeon': '리천: 중국 제일 살수',
    'risapic': '리사: 술집으로 위장한 킬러조직 이스크라의 마담이자 청부브로커',
    'akira': '아킬라: 이스크라 자유로운 영혼 계파장',
    'guseutapeu': '구스타프: 이스크라 차가운 눈 계파장 항상 강자 김신을 쫒는다',
    'geurolla': '그롤라: 이스크라 뜨거운 피 계파장',
    'cheonildo': '천일도: 캐슬호텔의 수장 과거 대국파 수장 이었으나 최민욱에 의해 대국파가 해산 되었다.',
    'juro':'주로: 천일도의 최측근 직속 암살조 손가락의 교관',
    'wangdam': '???: ???',
    'juwon': '주원: 통칭 디자이너',
    'ipildo': '이필도: 통칭 벨보이 천일도가 아낀다',
    'chominuk': '최민욱: 캐슬의 수장 과거 대국파를 밀어내고 캐슬을 설립하였다.',
    'mahagyeong': '마학영: 캐슬 홀딩스의 최고 전투원',
};

         let currentPage = 0; // 현재 페이지 인덱스
         const pages = document.querySelectorAll('.page'); // 모든 페이지 요소
         const infoSection = document.getElementById('info');
         const infoTitle = document.getElementById('info-title');
         const infoDescription = document.getElementById('info-description');
         const infoImages = document.getElementById('info-images');

         // 페이지 이동 함수
         function navigateToPage(pageIndex) {
             if (pageIndex < 0 || pageIndex >= pages.length) return; // 범위를 벗어나지 않도록
             const offset = -pageIndex * 100; // 이동할 거리 계산
             pages.forEach(page => {
                 page.style.transform = `translateY(${offset}vh)`; // 페이지 이동
             });
             currentPage = pageIndex; // 현재 페이지 업데이트
             infoSection.style.display = 'none'; // 정보 섹션 숨김
         }

         // 스크롤 이벤트 리스너
         window.addEventListener('wheel', function(event) {
             if (event.deltaY > 0) {
                 navigateToPage(currentPage + 1); // 아래로 스크롤 시 다음 페이지로 이동
             } else {
                 navigateToPage(currentPage - 1); // 위로 스크롤 시 이전 페이지로 이동
             }
         });
         function showInfo(org, event) {
    event.stopPropagation(); // 클릭 이벤트 전파 방지

    let description = '';
    let images = [];

    switch (org) {
        case '백의':
            description = '캐슬에 원한이 있는 사람들이 뭉쳐서 만든 조직 백의의 뜻은 전국의 남자들이 뜻을 하나로 모으니 (百意)약하지만 뭉치면 성을 무너뜨린다(白蟻) 이다.';
            images = ['kimsin.jpg', 'saroka.jpg', 'bolk.jpg'];
            break;
        case '하성':
            description = '하성건설과 하성기획이 계열사 이며 유일하게 회장 김태훈의 얼굴은 외부에 노출이된 공인이다';
            images = ['gimtaehun.jpg', 'ryujihak.jpg'];
            break;
        case '화진':
            description = '중국삼합회 간부 출신의 유우성이 수장인 조직 도우첸을 포함한 대부분이 홍콩 거지 출신 ';
            images = ['yuuseong.jpg', 'richeon.jpg'];
            break;
        case '이스크라':
            description = '러시아 블라디보스토크에 있는 주점 으로 위장한 세력 극동지역 최고의 킬러집단 소수정예 이지만 각각의 실력이 상위권이다. ';
            images = ['risapic.jpg', 'akira.jpg', 'guseutapeu.jpg', 'geurolla.jpg'];
            break;
        case '캐슬호텔':
            description = '전 대국파 회장인 천일도가 수장인 조직 과거 대국파는 전국을 휘어잡던 조직이었으나 최민욱과 강민성,차일국등이 속했던 파천에 의해 무너졌다.';
            images = ['cheonildo.jpg', 'wangdam.jpg', 'juro.jpg','juwon.jpg', 'ipildo.jpg'];
            break;
        case '캐슬홀딩스':
            description = '캐슬의 정점 과거 최민욱이 강민성등과 새운 파천이 대국파를 밀어내고 파천을 해체한후 세운 조직이다.';
            images = ['chominuk.jpg', 'mahagyeong.jpg'];
            break;
        default:
            description = '정보가 없습니다.';
    }

    // 정보 업데이트
    infoTitle.textContent = org;
    infoDescription.textContent = description;
    infoImages.innerHTML = ''; // 이전 이미지 제거

    // 이미지 추가
    images.forEach((src, index) => {
        const img = document.createElement('img');
        img.src = src; // 이미지 경로
        img.alt = org;

        // 각 인물에 대한 툴팁 내용 설정
        const characterName = src.split('.')[0]; // 이미지 파일명에서 이름 추출
        const tooltipText = characterTooltips[characterName]; // 툴팁 내용 가져오기

        // 이미지에 마우스 오버 이벤트 추가
        img.addEventListener('mouseover', function(event) {
            tooltip.textContent = tooltipText; // 인물 정보를 여기에 추가
            tooltip.style.display = 'block'; // 툴팁 보이기
            tooltip.style.left = event.pageX + 'px'; // 툴팁 위치
            tooltip.style.top = (event.pageY - 30) + 'px'; // 툴팁 위치 (약간 위로)

            // 이미지 가리기
            img.style.opacity = '0.5'; // 이미지 투명도 조정 (가리기 효과)
            img.style.zIndex = '5'; // 이미지의 z-index 낮추기
        });

        // 이미지에 마우스 아웃 이벤트 추가
        img.addEventListener('mouseout', function() {
            tooltip.style.display = 'none'; // 툴팁 숨기기
            img.style.opacity = '1'; // 이미지 원래 상태로 복원
            img.style.zIndex = '10'; // 이미지의 z-index 원래대로
        });

        infoImages.appendChild(img);
    });

    // 정보 섹션 보이기
    infoSection.style.display = 'block'; // 정보 섹션 보이기
}

         function hideInfo(event) {
    if (event.target === infoSection) {
        return; // 정보 섹션을 클릭한 경우 아무것도 하지 않음
    }
    infoSection.style.display = 'none'; // 정보 섹션 숨기기
}
     </script>
</body>
</html>
