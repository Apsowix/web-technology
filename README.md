## (C#)滑块验证码
![image](https://raw.githubusercontent.com/eatage/VerificationCode/master/src/demo.png)

### VerificationCode简介

>Verification is completed when the user drags the slider, and supports PC and mobile terminals. And save the time, accuracy, sliding trajectory and other information of the user verification process in the background. </br>
>The output verification code is in JSON format. The large picture is randomly mixed and spliced by cutting the original image into 10 parts horizontally and 2 parts vertically. A total of 20 pictures are randomly mixed and spliced. The original image is restored by shifting on the front end, and the confusion information is included in the JSON </br>
> **JSON format description：**</br>
&nbsp;&nbsp;&nbsp;&nbsp;*errcode：status code*</br>
&nbsp;&nbsp;&nbsp;&nbsp;*y：The y-axis coordinate of the cropped small image relative to the upper left corner*</br>
&nbsp;&nbsp;&nbsp;&nbsp;*array：Verification code image confusion rules*</br>
&nbsp;&nbsp;&nbsp;&nbsp;*imgx：Verification code image width*</br>
&nbsp;&nbsp;&nbsp;&nbsp;*imgy：Verification code image height*</br>
&nbsp;&nbsp;&nbsp;&nbsp;*small：Cropped small picture*</br>
&nbsp;&nbsp;&nbsp;&nbsp;*normal：Picture after obfuscated verification code*</br>
**Compatibility information: **Compatible with mainstream browsers, Safari on iPhone, WeChat built-in browser, and mainstream browsers on Android

#### JSON format example
```  json
{
  "errcode": 0,
  "y": 189,
  "array": "0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19",
  "imgx": 300,
  "imgy": 300,
  "small": "data:image/jpg;base64,/...",
  "normal":"data:image/jpg;base64,/..."
}
```
#### Usage example
```javascript
$("#__Verification").slide({
    imgspec: "200*100",
    successCallBack: function () {
        console.log("success");
        alert('You have been verified!');
    }
});
```
