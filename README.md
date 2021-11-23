# OpenCV

## [딥러닝]OpenCV를 활용한 이미지 & 영상 처리

### OpenCV01 : OpenCV 기초

#### (1) 이미지 불러오기

- *IMREAD()* 와 *matplotlib()* 으로 이미지 출력
- cv2.IMREAD_COLOR : 이미지를 칼라 이미지로 설정
- cv2.COLOR_RGB2BGR : RGB -> GBR
- cv2.IMREAD_GRAYSCALE : 흑백 이미지
- *cv2.cvtColor()* 함수로 칼라 이미지를 흑백 이미지로 변환

#### (2) 동영상 가져오기

- *VideoCapture()* : 비디오 파일이나 카메라를 연동
- 노트북 카메라 연동하여 이미지로 출력
- 녹화 기능 설정(속도, 화면크기, 코덱)하여 영상 녹화 기능 구현(CCTV 기능)

### OpenCV02 : OpenCV 응용

#### (1) OCR(광학문자판독)

- *OCR* : 이미지로 된 문자를 텍스트로 변환하는 작업
- Tessaract API, 구글 OCR API, Naver OCR API 등을 사용
- Tessaract API 다운로드 : https://github.com/UB-Mannheim/tesseract/wiki
- 파이썬용 Tessaract API 설치(pytesseract)

#### (2) 이미지에서 문자열 추출

- 영어 문장이 있는 이미지를 불러와 영어 문장 문자열 추출
- *lang = "eng"* : 언어 설정하여 원하는 언어의 문자열 추출
- tesseract API 사용할 때는 이진 이미지로 변경한 후에 사용하는 것을 권장(*글자가 흐릿할 경우 인식이 잘 안됨*) 

#### (3) 얼굴 영역 검출

- Cascade 분류기 사용(*CascadeClassifier()*)
- *haarcascade_frontalface_default.xml* -> haarcascade 얼굴 알고리즘 등록 
- scaleFactor : 확대비율만큼 확대해가면서 검색 -> 작은 값일수록 자세히 찾지만, 연산량이 증가
- minNeighbors : 후보 사각형이 유지해야 하는 최소 이웃의 수 -> 값이 클수록 덜 감지됨, 정확도는 증가
- 반환값 : 얼굴들의 좌상단좌표와 가로세로 크기가 튜플 형태로 반환
- 아이돌 블랙핑크 사진 얼굴 검출

#### (4) 얼굴에서 눈 검출

- *haarcascade_eye.xml* -> haarcascade 눈 알고리즘 등록 파일
- *VideoCapture()* 사용하여 노트북 카메라 연동 후 얼굴 영상에서 얼굴과 눈 검출
