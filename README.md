# Concrete Crack Detection Using Drone & Deep Learning

</br>

## Introduction

Crack on the surface of concrete is the one of the most clear signs of deterioration of concrete structure. Therefore, the concrete crack on the surface is the first target for the safety inspection, in most cases. Since the concrete crack has typical patterns, software can support the structual health monitoring through automatic crack detection. However, there has been mainly hardware-supported approach to safety inspection, not software-based one. Software-supported approach can save the cost, time and effort for saftey inspection through automatic evaluation on concrete image data.
</br></br>
Plus, UAV(Unmanned Aerial Vehicle), or drone, can amplify the synergy for software-based safety inspection because it can easily approach where human is impossible to reach. Especially, drone becomes particularly useful if used to examine the large scale concrete structure where safety inspectors are not able to reach every parts directly. That's why drone is recently being actively researched and utilized for large scale concrete structure health monitoring system. Therefore, the software tool for drone-based safety inspection is needed for the efficient examination in the future.
</br></br>
However, there isn't open source software yet to detect crack in the video recorded by drone which shoots the concrete structure surface. Hereby, I share my own concrete crack detection software for drone-based safety inspection. Single Shot Multibox Detector(SSD) is used for detecting cracks and Hybrid image processing is employed to estimate the crack width.

</br>

## Problem of Current Safety Inspection Methods
The Current problem of hardware-based concrete structure safety inspection.
the Korea Expressway Corporation(한국도로공사) U-BIROS
https://github.com/Garamda/SPARK/blob/master/images/U-BIROS.jpg

1. Automatation
</br>The assessment on data is still done by safety inspectors, even though the process can be automated through software because crack has typical patterns. Hardware can only help to collect data, but cannot make any decision on data instead of human.

2. Expensive 
1) The rental charge for under-bridge inspection vehicle : under-bridge inspection vehicle is used when inspecting the status of bridges. The problem is that the rental charges are expensive. It costs approximately 1,000 dollars(1,000,000 won) per one rental. The drone, however, demands only one purchase cost.<br>
2) Additional manpower for inspection : when inspecting bridges, normally 8 people are needed to control the traffic, 2 people to get on the arm of the vehicle to examine the under-bridge, and 1 person to drive the vehicle. Totally, 11 people are required to inspect one bridge, which means not only rental cost for the special vehicle, but also additional employees are needed when using the existing way of structual health monitoring. Only 1 person will be needed if using drone for same purpose.

</br>

## The Objective of SPARK
1. Crack detection : SPARK detects the cracks on the surface of the concrete structure.</br>
2. Crack width estimation & classification based on seriousness: SPARK estimate the width of the detected cracks, and reports the more serious crack first which has wider width than others. Basically, the crack of which width is more than 0.3mm is to be classified as "high risk crack", 0.3mm ~ 0.2mm as "low risk crack", and ~ 0.2mm as "minor crack.</br>
3. Crack location reporting : SPARK reports the actual location of the crack based on the flight log saved in the drone. With combining pixel information and the flight log, the location of crack can be calculated. It is useful for safety inspectors to know where the serious cracks locates which needs further precision diagnosis, before they physically approach to the target structure.

</br>
</br>

## User Benefit

1. Automation of Safety Inspection
</br>
The examination on structual health can be partially automated. SPARK selects which crack must be inspected based on width, which makes the further safety inspection done by human more efficient. SPARK "filters".
</br></br>
2. Reducing the time spent on Safety Inspection
</br>
추후 정밀 진단이 필요한 균열들의 위치와 심각한 정도를 사전에 알 수 있습니다. SPARK가 균열의 폭을 바탕으로 심각도가 높은 균열들부터 우선적으로 리포트하기 때문입니다. 따라서 안전 진단 시 소요 시간이 단축됩니다. 
</br></br>
3. One-stop System 
</br>
드론을 통한 데이터 촬영과 균열 검출 엔진을 연동 -> 실시간 처리 가능
구조물을 촬영부터 S/W를 통한 분석 작업 : 중단 없는 하나의 프로세스
</br>
4. Assuring the higher level of safety in the long term

</br></br>

## Performance
도표 사용, 실제 test 결과를 넣을 것(코드 사용하여 evaluation한 결과)

<br><br>

SPARK | Detection | ()
:---: | :---: | :---:
Crack Images from Google | d | d
d | d | d
d | d | d
d | d | d

<br><br>

SPARK | Width Estimation | ()
:---: | :---: | :---:
d | d | d
d | d | d
d | d | d

</br>

## Framework
1. Crack detection : Keras 2.2, Tensorflow 1.9.0, Python 3.6.6</br>
2. Crack width estimation : Scikit-image 0.14.0, Python 3.6.6</br>
3. Crack location reporting : </br>

</br>

## How to use
1. Crack detection : Install Anaconda, Keras, Tensorflow, Python -> 명령어 써주기
2. Crack width estimation : Install Scikit-image -> pip install -U scikit-image </br>
3. Crack location reporting : </br>
크랙 이미지 데이터 링크, h5 파일 링크, annotation file들 링크도 </br>
기본 설정에 기반한 내 친절한 설명이 들어가 있어야 함 -> 내 오픈소스 장점 어필 가능</br>
</br>

## Development Documentation
</br>
파일들간 관계를 설명, 중요한 파일들 위주로 설명 13 ~ 15 참조, EX) 얘는 학습용, 얘는 진단용, 얘는 UI, 얘는 라이브러리 등등 큰 범주들을 쓴 후 각 부분들을 들어가서 자세히, 폴더 구조로 해보자! 이게 제일 좋을듯 / 설정 파일(유저가 직접 변경해서 사용해야 하는 경우)은 
</br></br>

## Consultation
면담 결과를 표로 넣을것(객관적인 근거)
 | 대상 교량 | 시행 횟수 | 점검 수준 | 굴절차 필요 여부 | 비용(교량의 종류 및 길이에 따라 금액 산정이 달라지기는 하지만, 평균적으로)
| 필요 인원 | 소요 시간 |
:---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
d | d | d | d | d | d | d | d |
d | d | d | d | d | d | d | d |
d | d | d | d | d | d | d | d |
d | d | d | d | d | d | d | d |
d | d | d | d | d | d | d | d |
d | d | d | d | d | d | d | d |
</br>

## Reference
1. Liu, Wei, et al. "SSD: Single shot multibox detector." European conference on computer vision. Springer, Cham, 2016. (Link : https://arxiv.org/abs/1512.02325) </br>
2. Kim, Hyunjun, et al. "Concrete crack identification using a UAV incorporating hybrid image processing." Sensors 17.9 (2017): 2052. (Link : http://www.mdpi.com/1424-8220/17/9/2052/htm)

</br>

## LICENSE
오픈소스 어느부분 수정했는지 아주 큰 범주로만 
</br>
