# LLM

> Python으로 강원, 부산 맛집 정보를 데이터셋으로 저장하고, 이에 대해 사용자가 질의하면 답변을 생성하는 챗봇 저장소입니다.

## 개발 환경

* OS
  * Windows 10: 주요 코드 개발
  * Ubuntu 24.04: AWS에서 코드 테스트
* Language: Python 3.12
* Tools
  * Jupyter Lab: 주요 코드 개발
  * Google Colab Pro: LLaMa 모델 데이터셋 학습
 
## 사용 데이터

<a href="https://www.aihub.or.kr/aihubdata/data/view.do?currMenu=115&topMenu=100&aihubDataSe=data&dataSetSn=71607">관광 KVQA 데이터(동부권)</a>

## 프로젝트 특징

### 구현

* JSON 데이터를 LLaMa 모델에 맞게 세팅하기 위해, 알파카 모델로 데이터셋을 만들고 Hugging Face에 저장한다.
* 저장한 데이터를 API를 구축하여 웹 소켓을 생성한다. 사용자가 질의하면 챗봇 형식으로 알맞은 답변을 응답한다.

### 챗봇 서비스
* JSON 파일을 읽어서 Alpaca 방식으로 데이터를 추출한다.
  * annotation에서 Q&A에 사용할 instruction, input, ouptut 데이터프레임을 반환한다.
* 입력 질문을 받아 반복문으로 일치하는 질문이 있는지 찾아서 답변을 반환한다.
* JSON 파일 내 place와 질문을 합쳐 전체 질문 생성한다.
* 이에 관련된 질문이 있으면 해당 답변을 반환하고, 질문 내용이 없으면 답변을 찾을 수 없다는 메시지를 제공한다.

## 실행결과

### Postman API 구축 결과

![image](https://github.com/user-attachments/assets/d6d46ffe-dc5d-49f4-bd12-b96122125f7f)
![image](https://github.com/user-attachments/assets/e531504b-b001-4366-afcd-880040c101e2)

### 웹 소켓 서버 구축 결과

![image](https://github.com/user-attachments/assets/b7a8338f-286a-4a8c-8f34-a3941f5bb364)
![image](https://github.com/user-attachments/assets/62179163-5121-46da-86cc-1613c8100d37)

### 결과 데이터

<div><a href="https://huggingface.co/datasets/bin778/llm_midterm">Hugging Face Datasets</a></div>
<div><a href="https://huggingface.co/bin778/llama_llm_midterm/tree/main">LLaMa 모델 데이터셋 학습 결과</a></div>
