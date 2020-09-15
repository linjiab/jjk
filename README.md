# jjk
學習arouino的過程</p>
void setup(){}<--只執行一次，Arduino的初始設定 </p>
void loop(){}<--會重複執行，主程式的位子</p>
第一個指令</p>
pinMode(腳位，INPUT/OUTPUT);</p>
腳位模式設定 所使用的腳位設定為輸入或輸出</p>
設定腳位輸出(=0)，腳位輸入(=1)</p>
電路圖如下:</p>
![image](https://github.com/linjiab/jjk/blob/master/F63F541F-FA07-4F6B-992B-57657E60A8B5.jpeg)</p>
# 2020/09/08
四顆led燈同時閃爍 </p>
電路圖如下:</p>
![image](https://github.com/linjiab/jjk/blob/master/3C43C5C3-F08F-446A-87BA-AA9F76CF39A6.jpeg)</p>
# 2020/09/15
led跑馬燈 </p>
電路圖如下:</p>
![image](https://github.com/linjiab/jjk/blob/master/4C09AA91-E8FF-4E6C-A11C-27CAA004FFC7.jpeg)</p>
# 2020/09/15-2
led跑馬燈 </p>
電路圖如下:</p>
```c++
int LED=10;
void setup() {
  for (int i=1 ;i<10;i++)
   pinMode(i,OUTPUT); 
}
void loop() {
    // put your main code here, to run repeatedly: 
    for(int i=10; i>1; i--)
      digitalWrite(i,HIGH);
 if (LED>=1)
      digitalWrite(LED,LOW);
else
LED=10;
LED--;

delay(500);
}
```
![image](https://github.com/linjiab/jjk/blob/master/9DE3D0C7-FE75-4980-B5A8-2969A3BC5F92.jpeg)
# 2020/09/15-3
led跑馬燈 </p>
電路圖如下:</p>
```c++
int LED=1;
void setup() {
  for (int i=10 ;i>1;i--)
   pinMode(i,OUTPUT); 
}
void loop() {
    // put your main code here, to run repeatedly: 
    for(int i=1; i<10; i++)
      digitalWrite(i,HIGH);
 if (LED<=10)
      digitalWrite(LED,LOW);
else
LED=1;
LED++;

delay(100);
}
```
![image](https://github.com/linjiab/jjk/blob/master/5032EBAB-025A-4E30-8196-7A6F6AF086A8.jpeg)
