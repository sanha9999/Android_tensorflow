### ๋๊ธฐ ๐ค

ํ์๊ฐ์ด ํ๊ต์์ ์์์ ๋ค์ผ๋ฉด์ ์ด๊ณ ์๋ ์ด๋๋ , ์ฌ๋ฆ๋ฐค ๋ชจ๊ธฐ๊ฐ์ด ์ง์ฆ๋๋ ๊ฒ์ด ๋์๊ฒ ์ฐพ์์ ๋ฒ๋ ธ๋ค. ๋ฐ๋ก **์ํํ๊ฐ**์ด๋ค. ์ฑ์ ์ ๊ทธ๋ฆฌ ์ค์ํ๊ฒ ์ฌ๊ธฐ์ง๋ ์์ง๋ง ํ๋ก์ ํธํ ์ํํ๊ฐ์๊ธฐ๋๋ฌธ์ ๋ฅ๋ ฅ ์ฆ์ง์ ์ํด์, ํ์ง๋ง ์ด์ฌํํด์ผ๊ฒ ๋ค๊ณ  ๋ค์งํ ๊ฐ์ฅ ํฐ ์ด์ ๋ ์ ์๋์ ๋ ๋ฐ์ ๋๊ณ  ์ถ์ง ์์๊ธฐ ๋๋ฌธ์ด์๋ค..

๊ทธ๋์ ๊ฒฐ๊ตญ ์ฐ๋ฆฌ์กฐ๋ ์ธ๊ณต์ง๋ฅ์ ๊ณ๋ค์ธ ์์ 'ํฌ๋งํ์์ฉ'์ด๋ผ๊ณ  ๋ถ๋ฆฌ๋ ์ฑ์ ๋ง๋ค๊ธฐ๋ก ํ์๋ค. AI์ ๋ํด ๊ณต๋ถํ๋ ์ค ์ด์๊ธฐ ๋๋ฌธ์ ๋์๊ฒ๋ ํด๋ณผ๋งํ ๋์ ์ด์๊ณ  ๊ณต๋ถ์๋ค. ์น back-end์ model์ ์ฐ๋ํด ๋ณธ์ ์ ์์ด๋ Android app์์๋ ์ฒ์์ด์๊ธฐ ๋๋ฌธ์ด๋ค.

model ๊น์ง ์ด์ฐ์ด์ฐ ๋ง๋ค์์ด๋ model์ Android studio์ ์ฐ๊ฒฐํ  ๋ฐฉ๋ฒ์ ์ฐพ์ง๋ชปํด์ ํด๋งค๋ ์์ค์... app์ ๋ง๋ค๋ ์ธ์ด๋ Java๋ฅผ ์ฌ์ฉํ  ๊ฒ์ด๊ธฐ ๋๋ฌธ์ DL4J๊ฐ์ ํ๋ ์์ํฌ๋ฅผ ์ฐพ์๋ณด๋ค๊ฐ ์ฒ์์ผ๋ก TensorFlow Lite๋ผ๋ ๊ฒ์ ๋ค์ด๋ณด๊ฒ ๋์๋ค.

### TensorFlow Lite ๐ป

![](https://images.velog.io/images/sanha9999/post/27b8a37a-b0c4-4afb-9a92-faae65769006/image.png)

TensorFlow...๋ ๋ง์ด ๋ค์ด๋ณด๊ณ  ์ต์ํ ๋ผ์ด๋ธ๋ฌ๋ฆฌ์ด๋ค. ๊ธฐ๊ณ ํ์ต ๋ผ์ด๋ธ๋ฌ๋ฆฌ์ ์๋ ์ฐ๋งฅ ์ค ํ๋๋ก ๊ผฝํ๋ TensorFlow, ๋๋ ์ฒ์ ๊ธฐ๊ณ ํ์ต์ ๊ณต๋ถํ  ๋ ์ฌ์ฉํ์์ง๋ง ์ด๋ณด์์๋ ๊ทธ ๋น์ Session error๋ผ๋ ๋ฒฝ์ ๋งํ์ TensorFlow๋ฅผ ๋ง์ด ์ฐ์ง ์์์๋ค. ์๋ก ์ด ๊ธธ์๋ ๊ฒ ๊ฐ๋ค.
๊ทธ๋์ TensorFlow Lite๊ฐ ๋์ฒด ๋ญ๋๊ณ !! ๐ก

#### TensorFlow Lite๊ฐ ๋ญ๋๋ฉด~ ๐

๊ฐ๋จํ๋ค. TensorFlow Lite๋ ๋ชจ๋ฐ์ผ, ์๋ฒ ๋๋ ๋ฐ IoT  ๊ธฐ๊ธฐ์์ TensorFlow ๋ชจ๋ธ์ ๋ณํํ๊ณ  ์คํํ๋ ๋ฐ ํ์ํ ๋ชจ~~๋  ๋๊ตฌ๋ฅผ ์ ๊ณตํ๋ ํ๋ ์์ํฌ์ด๋ค. ๊ทธ๋ผ ๊ทธ๋ฅ TensorFlow๋ฅผ ์ฐ๋ฉด๋์ง ์ด ๊ฒ์ ์ ์ฌ์ฉํ๋?? ๋ฐ๋ก Lite๋ผ๋ ์ด๋ฆ์์ ์ ์ถํด๋ณผ ์ ์๋ฏ์ด TensorFlow๋ก ๋ง๋  model์ ์ปดํจํ ๋ฐ ๋ฉ๋ชจ๋ฆฌ๊ฐ ์ ํ์ ์ธ ๋ชจ๋ฐ์ผ/๊ธฐํ ์๋ฒ ๋๋ ๊ธฐ๊ธฐ์์ ํจ์จ์ ์ผ๋ก ์คํํ  ์ ์๋๋ก ๊ฒฝ๋ํ ํด์ฃผ๊ธฐ ๋๋ฌธ์ ์ฌ์ฉํ๋ ๊ฒ์ด๋ค. model์ ๋ณํํ๋ฉด ํ์ผ์ ํฌ๊ธฐ๋ ์ค์ด๋ค์ง๋ง model์ ์ ํ๋์๋ ์ํฅ์ ์ฃผ์ง ์๋๋ค๊ณ  ํ๋ค. 

๐ **ํ์ง๋ง TensorFlow Lite๋ Tensorflow์ ์ฐ์ฐ ์ค ์ผ๋ถ๋ง์ ์ง์ํ๊ธฐ ๋๋ฌธ์ ๋ชจ๋  ๋ชจ๋ธ์ ๋ณํํ  ์ ์๋ ๊ฒ์ ์๋๋ผ๊ณ  ํ๋ค.**
์ฐธ๊ณ  : [TensorFlow Lite ๋ณํ ๋ถ๊ฐ๋ฅ](https://www.tensorflow.org/lite/guide/ops_compatibility?hl=ko)

#### TensorFlow Lite ๋ณํ

๊ธฐ๋ณธ์ ์ธ TensorFlow Lite์ ๋ณํ ๋ฐฉ๋ฒ์ ์ด๋ ๋ค.

```python
import tensorflow as tf 

converter = tf.lite.TFLiteConverter.from_keras_model(์ ์ฅํ ๋ชจ๋ธ)
tflite_model = converter.convert() # ๋ณํ
open("๋ณํ๋ ๋ชจ๋ธ.tflite", "wb").write(tflite_model) # ๋ณํ๋ ๋ชจ๋ธ ์ ์ฅ
```

### ์ ๋ฆฌ ๐

์ด๋ฒ ๊ธ์์๋ TensorFlow Lite๊ฐ ๋ฌด์์ธ์ง์ ๋ณํ์ ํ๋ ๋ฐฉ๋ฒ์ ์๊ฒ๋์๋ค. ๋ค์ ๊ธ์์๋ Android studio์์ ์คํ์ ํ๋ ๋ฐฉ๋ฒ๊ณผ ์ง์  ์คํ์ ํด๋ณด๋๋ก ํ๊ฒ ๋ค. ๊ทธ๋ผ ๋ชจ๋ **<span style="color:green">Bamboo๐!!</span>**
