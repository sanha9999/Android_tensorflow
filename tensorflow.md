### 동기 🤔

평소같이 학교에서 수업을 들으면서 살고있던 어느날, 여름밤 모기같이 짜증나는 것이 나에게 찾아와 버렸다. 바로 **수행평가**이다. 성적을 그리 중요하게 여기지는 않지만 프로젝트형 수행평가였기때문에 능력 증진을 위해서, 하지만 열심히해야겠다고 다짐한 가장 큰 이유는 선생님의 눈 밖에 나고 싶지 않았기 때문이었다..

그래서 결국 우리조는 인공지능을 곁들인 소위 '킬링타임용'이라고 불리는 앱을 만들기로 하였다. AI에 대해 공부하는 중 이었기 때문에 나에게는 해볼만한 도전이었고 공부였다. 웹 back-end와 model을 연동해 본적은 있어도 Android app에서는 처음이었기 때문이다.

model 까진 어찌어찌 만들었어도 model을 Android studio에 연결할 방법을 찾지못해서 해매던 와중에... app을 만들때 언어는 Java를 사용할 것이기 때문에 DL4J같은 프레임워크를 찾아보다가 처음으로 TensorFlow Lite라는 것을 들어보게 되었다.

### TensorFlow Lite 💻

![](https://images.velog.io/images/sanha9999/post/27b8a37a-b0c4-4afb-9a92-faae65769006/image.png)

TensorFlow...는 많이 들어보고 익숙한 라이브러리이다. 기계 학습 라이브러리의 양대 산맥 중 하나로 꼽히는 TensorFlow, 나도 처음 기계 학습을 공부할 때 사용하였지만 초보자였던 그 당시 Session error라는 벽에 막혀서 TensorFlow를 많이 쓰지 않았었다. 서론이 길었던 것 같다.
그래서 TensorFlow Lite가 대체 뭐냐고!! 😡

#### TensorFlow Lite가 뭐냐면~ 😅

간단하다. TensorFlow Lite는 모바일, 임베디드 및 IoT  기기에서 TensorFlow 모델을 변환하고 실행하는 데 필요한 모~~든 도구를 제공하는 프레임워크이다. 그럼 그냥 TensorFlow를 쓰면되지 이 것을 왜 사용하냐?? 바로 Lite라는 이름에서 유추해볼 수 있듯이 TensorFlow로 만든 model을 컴퓨팅 및 메모리가 제한적인 모바일/기타 임베디드 기기에서 효율적으로 실행할 수 있도록 경량화 해주기 때문에 사용하는 것이다. model을 변환하면 파일의 크기는 줄어들지만 model의 정확도에도 영향을 주지 않는다고 한다. 

📌 **하지만 TensorFlow Lite는 Tensorflow의 연산 중 일부만을 지원하기 때문에 모든 모델을 변환할 수 있는 것은 아니라고 한다.**
참고 : [TensorFlow Lite 변환 불가능](https://www.tensorflow.org/lite/guide/ops_compatibility?hl=ko)

#### TensorFlow Lite 변환

기본적인 TensorFlow Lite의 변환 방법은 이렇다.

```python
import tensorflow as tf 

converter = tf.lite.TFLiteConverter.from_keras_model(저장한 모델)
tflite_model = converter.convert() # 변환
open("변환된 모델.tflite", "wb").write(tflite_model) # 변환된 모델 저장
```

### 정리 😉

이번 글에서는 TensorFlow Lite가 무엇인지와 변환을 하는 방법을 알게되었다. 다음 글에서는 Android studio에서 실행을 하는 방법과 직접 실행을 해보도록 하겠다. 그럼 모두 **<span style="color:green">Bamboo🎍!!</span>**
