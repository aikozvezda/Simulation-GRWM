# Simulation-GRWM
이 프로젝트는 "Simulation GRWM (Get Ready With Me)"입니다. GRWM는 외출 전 메이크업, 헤어, 패션 등의 준비 과정을 공유한다는 뜻입니다. 요즘 sns에서 유행하는 영상입니다. 
사람들이 가상 환경에서 다양한 스타일링 선택을 시도하고, 다른 장소에 나가는 시뮬레이션을 할 수 있도록 설계되었습니다. 이 프로그램은 사용자가 자신의 얼굴 사진을 캡처한 후, 여러 가지 스타일링 옵션을 적용해보는 일련의 단계들을 포함합니다.

각 단계를 요약하면 다음과 같습니다:<br/>

얼굴 사진 캡처:<br/>
사용자는 자신의 얼굴 사진을 웹캠을 통해 캡처합니다. 이 이미지는 이후 단계에서 사용됩니다.<br/>
![다운로드 (7)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/52b515e6-39f8-402c-ba9a-4eb8c73cc732)<br/>

얼굴 랜드마크 탐지:<br/>
Dlib의 얼굴 인식기와 랜드마크 탐지기를 사용하여 얼굴의 주요 특징점 (눈, 코, 입 등)을 감지합니다.이 랜드마크 정보를 바탕으로 얼굴의 윤곽선 경계를 계산합니다.<br/>
![다운로드 (6)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/7e333c3f-5037-4fa7-94fb-df56176c8dbe)<br/>

헤어스타일 적용:<br/>
사용자는 헤어스타일 이미지를 업로드합니다. 다음과 같은 두 머리 스타일을 사용했습니다.<br/>
![긴웨이브머리](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/25dd2346-b5b6-47a0-ad39-072f53ca5ef5)
![긴생머리](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/59c049a6-b297-4a35-9d45-cc3fcbf59939)<br/>

갈색 계열의 머리카락 부분만 추출하여, 얼굴 좌우 경계에 맞춰 크기를 조절하고, 얼굴 이미지에 합성합니다.<br/>
![다운로드 (5)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/b1fd2932-bb5a-49dc-a4d5-001a9c4116ac)
![다운로드 (8)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/b9c94c5d-a6cb-4d0c-a3fb-c5340a2a498e) <br/>

립 색상 선택:<br/>
사용자는 립스틱 색상을 선택합니다 (빨간색 또는 핑크색).선택한 색상을 기반으로 입술 영역에 색상을 적용합니다.<br/>
![다운로드 (4)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/cac74aca-7dc6-4cdc-ad8d-71f0b5f69443)
![다운로드 (9)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/b2f5d089-4a91-4a94-9708-40b797d0f277) <br/>

렌즈 색상 선택:<br/>
사용자는 눈동자 색상을 선택합니다 (회색, 검정색, 갈색, 초록색). 선택한 색상을 기반으로 눈동자에 색상을 적용합니다. 렌즈 색을 여자들이 좋아하는 색으로 최대한 맞췄습니다.<br/>
![다운로드 (3)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/60b2ffea-875c-4e42-8070-79d3b3b37a1c)
![다운로드 (12)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/e401dd60-1201-4763-8fc5-4cb1b2550420)
![다운로드 (11)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/fb4d9458-1eb2-48c8-ad9f-2e8eceebca6f)
![다운로드 (13)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/d904600b-63c8-48b8-9436-479f7c7575a9)

<br/>배경 제거 및 변경:<br/>
MediaPipe Pose 모델을 사용하여 이미지에서 사람을 분리합니다. 배경을 투명하게 만든 후, 사용자는 여러 배경 옵션 중 하나를 선택합니다 (카페, 클럽, 바다, 숲). 배경 사진을 Chat GPT로 생성했습니다:<br/>
![cafe](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/b4471e91-44ef-4d79-b6ea-541afb645970)
![forest](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/09e7a62b-05b5-448b-b186-1090f9e68ee0)
![ocean](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/a8d11613-bac6-4331-bb3a-2f6ad941a1f6)
![bar](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/7e43a2f0-7a8e-43c1-9a2c-7c77b7c04e27)<br/>
선택한 배경 이미지와 얼굴 이미지를 합성하여 최종 이미지를 생성합니다. 각 단계의 결과 이미지는 사용자에게 출력되며, 최종적으로 선택한 배경과 함께 스타일링이 적용된 이미지를 저장할 수 있습니다.<br/>
![다운로드 (2)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/7c631f24-c54c-4029-82ad-b7dc05b12a6d)
![다운로드 (1)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/b331d24c-4715-4eaf-afb5-b0075c514115)
![다운로드 (15)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/66527a7e-2987-465c-a040-4d1dc9d478cc)
![다운로드 (14)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/c3f3ef05-7b0a-4464-86b2-ef9766cc605d)
![다운로드 (16)](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/9ade0c3c-ffb6-48cb-84e8-01e5c7b4dcd5)
<br/><br/>


주요 코드 설명:<br/>
얼굴 캡처 및 랜드마크 탐지: 얼굴 이미지를 캡처하고, dlib을 사용해 얼굴의 특징점을 감지합니다.<br/>
헤어스타일 합성: 사용자가 업로드한 헤어스타일 이미지를 얼굴 랜드마크를 기반으로 크기 조절 및 합성합니다.<br/>
립스틱 색상 적용: 사용자가 선택한 립스틱 색상을 얼굴 이미지의 입술 부분에 적용합니다.<br/>
렌즈 색상 적용: 사용자가 선택한 렌즈 색상을 눈동자 부분에 적용합니다.<br/>
배경 제거 및 변경: MediaPipe Pose 모델을 사용해 사람을 배경에서 분리하고, 선택한 배경 이미지와 합성합니다.<br/><br/>

코드에서 사용된 주요 라이브러리와 모델 출처:<br/>
Dlib:얼굴 인식 및 랜드마크 탐지 기능에 사용된 라이브러리입니다.Dlib의 얼굴 랜드마크 모델 (shape_predictor_68_face_landmarks.dat)은 Dlib 웹사이트에서 다운로드받았습니다.<br/>
OpenCV: 이미지 처리, 마스크 생성, 합성 등에 사용된 라이브러리입니다.<br/>
MediaPipe:포즈 인식 및 세그멘테이션 마스크 생성에 사용된 Google에서 제공하는 오픈소스 라이브러리입니다.<br/>
MobileNet-SSD 모델: 객체 감지에 사용된 모델입니다. 특정 GitHub 저장소에서 다운로드했습니다. (https://github.com/chuanqi305/MobileNet-SSD)<br/>
JavaScript 및 HTML: 웹캠을 통해 사진을 캡처하는 부분은 JavaScript와 HTML을 사용하여 구현되었습니다.<br/>
Google Colab: google.colab.patches 모듈을 사용해 JavaScript 코드를 실행하여 웹캠을 통해 이미지를 캡처합니다. <br/>
Chat GPT 및 Claude: 코드 생성 및 사진 생성 과정에서 많이 사용되었습니다.

모든 작업을 Colab을 이용해서 진행했습니다:https://colab.research.google.com/drive/1o771NeYDXftG3OXEVE1-s3JjLI7eFuKm?usp=sharing
shape_predictor_68_face_landmarks.dat.bz2 파일은 Dlib 라이브러리에서 제공하는 얼굴 랜드마크 예측 모델 파일입니다. 

아래 코드에서 파일 업로드를 해야 합니다.
![image](https://github.com/aikozvezda/Simulation-GRWM/assets/144213771/7f09400b-c778-434d-b104-7639ef7a96b1)

밑에 다운로드 URL 주소가 있습니다. 이 파일을 업로드 하시면 됩니다. **(다운로드 안하면 동작 안함)**
https://github.com/italojs/facial-landmarks-recognition/raw/master/shape_predictor_68_face_landmarks.dat

이 프로젝트를 하면서 정말 재미있고 기억에 오래 남을 좋은 시간을 보냈습니다. 결과가 생각보다 부실하고 웃깁니다.
