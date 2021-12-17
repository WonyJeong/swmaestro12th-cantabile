# CANTABILE-Client
Cantabile-client 레포지토리는 SW마에스트로 12기 Page-Turner팀에서 기획한 피아노 연습 어플리케이션 입니다. Flutter 프레임 워크를 이용한 iOS/Android 앱 개발이 본 과정 시작 이후 진행되었으며, 현재 구글 PlayStore와 Apple AppStore에 배포되었습니다.    
<p align="center">
<img src=https://user-images.githubusercontent.com/59948675/146494279-e569c158-3721-4043-a436-78e27d84a8de.png>
<p>
  
[PlayStore에서 Cantabile 확인하기](https://play.google.com/store/apps/details?id=tech.pageturner.cantabile)   <br>
[AppStore에서 Cantabile 확인하기](https://apps.apple.com/kr/app/cantabile/id1591722334 )

# 개발환경
Cantabile App은 Flutter 프레임 워크 v2.2.1, Dart SDK v2.12.0으로 개발이 진행되었습니다.

# SetUp Cantabile
Cantabile는 내부 복잡한 기능을 구현하기 위해 다양한 pub.dev 오픈소스 라이브러리를 활용해 개발이 진행되었습니다. 대부분 소스는 네이티브 설정을 필요로 하지 않지만, Device Permission을 다루는 모듈(FPAD, Audio Player 등)의 기본 설정을 필요로 합니다.

# Directory Structure
Cantabile의 상태관리 라이브러리는 [GetX](https://pub.dev/packages/get) 적극적으로 활용하여 개발이 진행되었습니다. 때문에 GetX 패턴을 기반으로 프로젝트 구조가 설계되었습니다. 
<p align="center">
<img src=https://user-images.githubusercontent.com/59948675/146494360-2f9459b1-2d9e-4de6-87dd-89220e8d96dc.png>
</p>
위 이미지는, 현재 저장소의 Structure를 간단하게 표현한 다이어그램입니다.

# Cantabile UI
Cantabile App 내 주요 화면에 대한 설명입니다. App을 구성하는 화면 중 중요하지 않다고 판단된 화면은 추가하지 않았습니다. 많은 화면을 확인하고자 한다면, 상단의 앱 다운로드 링크를 통해 모바일 환경에서 확인해주세요.

|화면 이름|화면|화면 설명|
|:---:|:---:|:---|
|홈|![image](https://user-images.githubusercontent.com/59948675/146494409-0e1c6f29-6884-4af0-b81c-876fe00933be.png)|- Cantabile App 로그인 화면 입니다<br>- 구글, 카카오, 애플 총 3가지 플랫폼을 통해 로그인이 가능합니다.|
|홈|![image](https://user-images.githubusercontent.com/59948675/146494657-a76f6598-a3fa-4077-96d8-bacd0169a3b5.png)|- 처음 확인할 수 있는 앱 화면입니다.<br>- 사용자 악보 추천 섹션이 제공됩니다. 현재 총 9가지 섹션이 제공되고 있습니다.|
|악보 선택|![image](https://user-images.githubusercontent.com/59948675/146494425-b118832e-cb1a-485c-b79d-b40861c46382.png)|- 사용자가 악보를 선택했을 때 보여지는 화면입니다.<br>Bottom Sheet로 화면을 구성하였으며, 이 화면 내에서는 악보 난이도 선택, 악보 연습 모드를 선택할 수 있습니다.|
|연습모드 - 피드백 모드|![image](https://user-images.githubusercontent.com/59948675/146494435-2e0d5482-b0d8-4149-97fd-eda99fd2189d.png)|- 연습모드 - 피드백 모드입니다.<br>- 피드백 모드를 선택한 후, 상단의 플레이 버튼을 누르면 인공지능 피아노 음향 인식 기능 동작합니다.<br>회색 커서는 다음 쳐야 할 Column을 의미합니다. Column 상에 그려진 피아노 건반을 올바르게 연주하면 다음 Column으로 커서가 Shift합니다.<br>- 오른쪽 상단의 손 모양 버튼을 통해 연습 할 손을 선택할 수 있습니다.|
|연습모드 - 자동 연주 모드|![image](https://user-images.githubusercontent.com/59948675/146494445-6c657816-92ca-43e0-a8f8-90fe0363e0d8.png)|- 연습모드 - 자동 연주 모드입니다. <br>- 자동 연주 모드는 현재 설정된 템포의 속도로 자동으로 mp3가 플레이 되며 악보가 오토 스크롤 되는 연습 화면입니다.<br> - 사용자 스크롤 위치 기반 데이터 매핑이 되어 있기 때문에 어느 위치로 스크롤을 하던, 그 위치에 맞는 플레이가 가능합니다.|
