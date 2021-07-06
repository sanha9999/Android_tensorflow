### 그 이후 🙁

TensorFlow Lite를 알게 된 이후로 Android에서 model을 어떻게 적용하는지는 알았으나...가장 중요한 일 이었던 기본 이미지를 텐서 이미지로 변환하는 것에 대한 많은 고뇌와 구글링이 있었다.
하지만 난 가장 중요한 것을 까먹고 있었다!! TensorFlow Lite를 알았으면서도 바보같이 다른 방법을 찾고 있었다. TensorFlow Lite에 당연히 그런 도구들이 있겠지!! 이 사실을 조금만 더 빨리 깨달았었으면 좋았을텐데...😫

### TensorFlow Lite에서의 데이터 처리 📲

**📌 아래 나올 데이터 처리 라이브러리들은 Android에서만 지원한다!!**




#### Android studio에 model 추가

일단 Android Studio에 빈 프로젝트 하나를 생성한다.

<center><img src="https://images.velog.io/images/sanha9999/post/c5c61898-196f-46ad-83ef-fdee4449ff03/image.png" width="80%" height="30%"></center>


File > New > Folder > Assets Folder를 눌러 app 폴더에 assets 폴더를 새로 만들어준다. 아래 사진에 보이는 것 같이 폴더 이미지에 **<span style="color:Orange">주황색 네모</span>**같은 표시가 있어야 잘 만들어 진 것이다.

![](https://images.velog.io/images/sanha9999/post/5c829ea3-5a69-4baa-bcfb-9e9c876d5869/image.png)

그리고 우리가 .tflite파일로 저장한 모델을 Android studio의 assets 폴더에 복사한다.
이 작업으로 우리는 Android studio에 model을 추가했다.





#### gradle 설정하기

다음으로는 모델 파일이 압축되지 않도록 gradle파일을 수정해줘야한다. Gradle Scripts를 보면 build.gradle 파일이 두개가 있는데 **build.gradle(Module: app)파일**을 수정해야한다!!! 

```java
android {
    // 다른 settings

    // 압축되지 않도록 설정
    aaptOptions {
        noCompress "tflite"
    }

}

dependencies {
    // 다른 코드들~

    // Import tflite 종속성
    
    implementation 'org.tensorflow:tensorflow-lite:0.0.0-nightly-SNAPSHOT'
    // GPU 라이브러리...이것은 선택사항
    implementation 'org.tensorflow:tensorflow-lite-gpu:0.0.0-nightly-SNAPSHOT'
    implementation 'org.tensorflow:tensorflow-lite-support:0.0.0-nightly-SNAPSHOT'
}
```

다 입력했으면 오른쪽 상단에 [Sync Now]를 눌러주어 동기화를 진행한다. 


#### 이미지 조작과 변환

내가 가장 고민한 문제가 바로 이것이었다. 이미지의 resize와 이미지를 텐서이미지로 변환하는 것을 어떻게 하는지 굉장히 고민을 했었다. 그런데 알고보니까 그렇게 어렵지 않다는 것을 깨달았다. 같이 해보자!!

```java
import org.tensorflow.lite.support.image.ImageProcessor;
import org.tensorflow.lite.support.image.TensorImage;
import org.tensorflow.lite.support.image.ops.ResizeOp;
// ImageProcessor를 정의한다.
ImageProcessor imageProcessor =
    new ImageProcessor.Builder()
        .add(new ResizeOp(224, 224, ResizeOp.ResizeMethod.BILINEAR))
        .build();
// 이미지를 Tensor Image로 바꾼다.
TensorImage tImage = new TensorImage(DataType.데이터타입);

// Processing
tImage.load(bitmap);
tImage = imageProcessor.process(tImage);
```

위의 코드로 기본 이미지를 텐서 이미지로 변환을 할 수 있다.

### 정리 😉

이번 글에서는 Android studio에서 어떻게 모델을 연동하는지와 기본 이미지를 Tensor Image로 변환하는 방법을 알아보았다. 다음 글에서는 Android studio에서 predict를 하는 방법을 리뷰해보도록 하겠다. 그럼 모두 **<span style="color:green">Bamboo</span>**🎍!!

