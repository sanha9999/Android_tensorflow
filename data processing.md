### ๊ทธ ์ดํ ๐

TensorFlow Lite๋ฅผ ์๊ฒ ๋ ์ดํ๋ก Android์์ model์ ์ด๋ป๊ฒ ์ ์ฉํ๋์ง๋ ์์์ผ๋...๊ฐ์ฅ ์ค์ํ ์ผ ์ด์๋ ๊ธฐ๋ณธ ์ด๋ฏธ์ง๋ฅผ ํ์ ์ด๋ฏธ์ง๋ก ๋ณํํ๋ ๊ฒ์ ๋ํ ๋ง์ ๊ณ ๋์ ๊ตฌ๊ธ๋ง์ด ์์๋ค.
ํ์ง๋ง ๋ ๊ฐ์ฅ ์ค์ํ ๊ฒ์ ๊น๋จน๊ณ  ์์๋ค!! TensorFlow Lite๋ฅผ ์์์ผ๋ฉด์๋ ๋ฐ๋ณด๊ฐ์ด ๋ค๋ฅธ ๋ฐฉ๋ฒ์ ์ฐพ๊ณ  ์์๋ค. TensorFlow Lite์ ๋น์ฐํ ๊ทธ๋ฐ ๋๊ตฌ๋ค์ด ์๊ฒ ์ง!! ์ด ์ฌ์ค์ ์กฐ๊ธ๋ง ๋ ๋นจ๋ฆฌ ๊นจ๋ฌ์์์ผ๋ฉด ์ข์์ํ๋ฐ...๐ซ

### TensorFlow Lite์์์ ๋ฐ์ดํฐ ์ฒ๋ฆฌ ๐ฒ

**๐ ์๋ ๋์ฌ ๋ฐ์ดํฐ ์ฒ๋ฆฌ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ค์ Android์์๋ง ์ง์ํ๋ค!!**




#### Android studio์ model ์ถ๊ฐ

์ผ๋จ Android Studio์ ๋น ํ๋ก์ ํธ ํ๋๋ฅผ ์์ฑํ๋ค.

<center><img src="https://images.velog.io/images/sanha9999/post/c5c61898-196f-46ad-83ef-fdee4449ff03/image.png" width="80%" height="30%"></center>


File > New > Folder > Assets Folder๋ฅผ ๋๋ฌ app ํด๋์ assets ํด๋๋ฅผ ์๋ก ๋ง๋ค์ด์ค๋ค. ์๋ ์ฌ์ง์ ๋ณด์ด๋ ๊ฒ ๊ฐ์ด ํด๋ ์ด๋ฏธ์ง์ **<span style="color:Orange">์ฃผํฉ์ ๋ค๋ชจ</span>**๊ฐ์ ํ์๊ฐ ์์ด์ผ ์ ๋ง๋ค์ด ์ง ๊ฒ์ด๋ค.

![](https://images.velog.io/images/sanha9999/post/5c829ea3-5a69-4baa-bcfb-9e9c876d5869/image.png)

๊ทธ๋ฆฌ๊ณ  ์ฐ๋ฆฌ๊ฐ .tfliteํ์ผ๋ก ์ ์ฅํ ๋ชจ๋ธ์ Android studio์ assets ํด๋์ ๋ณต์ฌํ๋ค.
์ด ์์์ผ๋ก ์ฐ๋ฆฌ๋ Android studio์ model์ ์ถ๊ฐํ๋ค.





#### gradle ์ค์ ํ๊ธฐ

๋ค์์ผ๋ก๋ ๋ชจ๋ธ ํ์ผ์ด ์์ถ๋์ง ์๋๋ก gradleํ์ผ์ ์์ ํด์ค์ผํ๋ค. Gradle Scripts๋ฅผ ๋ณด๋ฉด build.gradle ํ์ผ์ด ๋๊ฐ๊ฐ ์๋๋ฐ **build.gradle(Module: app)ํ์ผ**์ ์์ ํด์ผํ๋ค!!! 

```java
android {
    // ๋ค๋ฅธ settings

    // ์์ถ๋์ง ์๋๋ก ์ค์ 
    aaptOptions {
        noCompress "tflite"
    }

}

dependencies {
    // ๋ค๋ฅธ ์ฝ๋๋ค~

    // Import tflite ์ข์์ฑ
    
    implementation 'org.tensorflow:tensorflow-lite:0.0.0-nightly-SNAPSHOT'
    // GPU ๋ผ์ด๋ธ๋ฌ๋ฆฌ...์ด๊ฒ์ ์ ํ์ฌํญ
    implementation 'org.tensorflow:tensorflow-lite-gpu:0.0.0-nightly-SNAPSHOT'
    implementation 'org.tensorflow:tensorflow-lite-support:0.0.0-nightly-SNAPSHOT'
}
```

๋ค ์๋ ฅํ์ผ๋ฉด ์ค๋ฅธ์ชฝ ์๋จ์ [Sync Now]๋ฅผ ๋๋ฌ์ฃผ์ด ๋๊ธฐํ๋ฅผ ์งํํ๋ค. 


#### ์ด๋ฏธ์ง ์กฐ์๊ณผ ๋ณํ

๋ด๊ฐ ๊ฐ์ฅ ๊ณ ๋ฏผํ ๋ฌธ์ ๊ฐ ๋ฐ๋ก ์ด๊ฒ์ด์๋ค. ์ด๋ฏธ์ง์ resize์ ์ด๋ฏธ์ง๋ฅผ ํ์์ด๋ฏธ์ง๋ก ๋ณํํ๋ ๊ฒ์ ์ด๋ป๊ฒ ํ๋์ง ๊ต์ฅํ ๊ณ ๋ฏผ์ ํ์๋ค. ๊ทธ๋ฐ๋ฐ ์๊ณ ๋ณด๋๊น ๊ทธ๋ ๊ฒ ์ด๋ ต์ง ์๋ค๋ ๊ฒ์ ๊นจ๋ฌ์๋ค. ๊ฐ์ด ํด๋ณด์!!

```java
import org.tensorflow.lite.support.image.ImageProcessor;
import org.tensorflow.lite.support.image.TensorImage;
import org.tensorflow.lite.support.image.ops.ResizeOp;
// ImageProcessor๋ฅผ ์ ์ํ๋ค.
ImageProcessor imageProcessor =
    new ImageProcessor.Builder()
        .add(new ResizeOp(224, 224, ResizeOp.ResizeMethod.BILINEAR))
        .build();
// ์ด๋ฏธ์ง๋ฅผ Tensor Image๋ก ๋ฐ๊พผ๋ค.
TensorImage tImage = new TensorImage(DataType.๋ฐ์ดํฐํ์);

// Processing
tImage.load(bitmap);
tImage = imageProcessor.process(tImage);
```

์์ ์ฝ๋๋ก ๊ธฐ๋ณธ ์ด๋ฏธ์ง๋ฅผ ํ์ ์ด๋ฏธ์ง๋ก ๋ณํ์ ํ  ์ ์๋ค.

### ์ ๋ฆฌ ๐

์ด๋ฒ ๊ธ์์๋ Android studio์์ ์ด๋ป๊ฒ ๋ชจ๋ธ์ ์ฐ๋ํ๋์ง์ ๊ธฐ๋ณธ ์ด๋ฏธ์ง๋ฅผ Tensor Image๋ก ๋ณํํ๋ ๋ฐฉ๋ฒ์ ์์๋ณด์๋ค. ๋ค์ ๊ธ์์๋ Android studio์์ predict๋ฅผ ํ๋ ๋ฐฉ๋ฒ์ ๋ฆฌ๋ทฐํด๋ณด๋๋ก ํ๊ฒ ๋ค. ๊ทธ๋ผ ๋ชจ๋ **<span style="color:green">Bamboo</span>**๐!!

