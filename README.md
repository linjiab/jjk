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
# 2020/09/15-4
led呼吸燈 </p>
電路圖如下:</p>
```c++
int b = 0;
int f = 1;
void setup() {
  pinMode(5,OUTPUT);
}

void loop() {
  analogWrite(5,b);
  b = b + f;
  if (b <=0)
     f = -f;
  if (b >= 255)
    f = -f;
  delay(5);
}
```
![image](https://github.com/linjiab/jjk/blob/master/24535E85-6D40-43D5-B7CB-A48F70015902.jpeg)
# 2020/09/22-1
按鈕讓LED亮起,reset鍵滅 </p>
電路圖如下:</p>
```c++
void setup() {
 pinMode(2,INPUT);
 pinMode(3,OUTPUT);
 digitalWrite(3,HIGH);
 digitalWrite(2,HIGH);
}

void loop() {
  if(digitalRead(2) == 0)
  {
    digitalWrite(3,LOW);
  }
  /*else 
  {
    digitalWrite(3,HIGH);
  }*/
}
```
![image](https://github.com/linjiab/jjk/blob/master/B0ADCEE6-61AF-4D8F-BB1C-1E06DF3E76D4.jpeg)
# 2020/09/22-2
切換LED亮或滅 </p>
電路圖如下:</p>
```c++
int j=1,jj=1;
void setup() {
 pinMode(2,INPUT);
 pinMode(3,OUTPUT);
 digitalWrite(2,HIGH);
 digitalWrite(3,HIGH);
}
void loop() {
  if(!digitalRead(2))
  {
    while(!digitalRead(2))
    delay(20);
    jj=0;
  }
  else
  {
    if(!jj)
    {
      jj=1;
      j^=1;
    }
  }
  digitalWrite(3,j);
}
```
![image](https://github.com/linjiab/jjk/blob/master/B0ADCEE6-61AF-4D8F-BB1C-1E06DF3E76D4.jpeg)
# 2020/09/22-3
</p>
電路圖如下:</p>
```c++
byte ledpin[8]={3,4,5,6,7,8,9,10};
int jj =1 ,a=-1;

void setup()
{
  for(int i=0;i<8;i++)pinMode(ledpin[i],OUTPUT);
  for(int i=0;i<8;i++)digitalWrite(ledpin[i],1);
  pinMode(2,INPUT);
  digitalWrite(2,1);
}

void loop() 
{
  if(!digitalRead(2))
  {
    while(!digitalRead(2))delay(20);
    if(!jj)
    {
      a++;
      jj=1;
    }
  }
  else
  {
    jj=0;
    switch(a)
    {
      case 0:
        for(int i=0;i<8;i++)
        {
          for(int j=0;j<8;j++)digitalWrite(ledpin[j],1);
          digitalWrite(ledpin[i],0);
          delay(100);
        }
      break;
       
      case 1:
        for(int i=7;i>-1;i--)
          {
            for(int j=0;j<8;j++)digitalWrite(ledpin[j],1);
            digitalWrite(ledpin[i],0);
            delay(100);
          }
      break;
        
      case 2:
        for(int i=0;i<8;i++)digitalWrite(ledpin[i],1);
      break;
       
      case 3:
        a=0;
      break;
    }
  }
}
```
![image]()
