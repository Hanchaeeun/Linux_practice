# 슈퍼컴퓨터 기반 유전체 변이분석 파이프라인 최적화 기술 개발

[수원대학교, Kisti] 2021.04.01~2021.10.31


<br/>

>Kisti Institutional Repository :  https://repository.kisti.re.kr/handle/10580/17091

> (2) variant calling 파트 담당으로 프로젝트에 참여했던 일부 코드와 교내 포스트 발표자로 만들었던 포스터를 업로드 합니다. 

## purpose
![전체과정](https://user-images.githubusercontent.com/72204267/195063720-830a255e-44ee-440c-acc3-e04e3b13c113.png)

전장유전체 데이터의 양은 점점 증가하지만, 기존의 전장유전체 변이분석 파이프라인은 슈퍼컴퓨터에 최적화 되어 있지 않아 효율성이 떨어졌다.
본 연구는 슈퍼컴퓨터에 적합한 전장유전체 변이분석 파이프라인을 개발해 변이분석의 효율성을 높이기 위해 진행되었다.<br/>
전장유전체 분석에서 시간이 많이 소요되는 핵심 과정은 alignment, preprocessing, variant calling 파트로,
각 단계에서 사용할 수 있는 소프트웨어들을 슈퍼컴퓨터에서 병렬화 하고 최적의 파라미터 값을 발굴하여 수행속도를 향상 시킨 결과를 얻었다.

## System environment
KISTI 슈퍼컴퓨터 5호기 누리온 (05-Nurion-KNL)
### OS
centOS 7
### Terminal program
MobaXterm

## assignment
- Linux 기초 정리
- 유전체 데이터 분석에 대한 이해
  - 유전체 분석 도구 사용법
  - linux 활용 스크립트 구현
- PBS(스케줄러)를 이용한 작업 실행(Nurion)
- 슈퍼컴퓨터에 최적화된 Multi-threading 변이분석 파이프라인 구축

## create scripts

1. Setting the environment<br/>
    anaconda3에 python3.8 가상환경 생성 후 접속해 BWA툴 다운로드 
  
2. sampling  bam<br/>
    bam file을 입력받아 크기를 10%~100%로 랜덤 추출한 bam file 출력
  
3. Strelka2<br/>
    돌연변이 분석 툴인 Strelka2를 설치 후 Germline, Somatic Calling 후 변이파일(VCF) 출력
    
4. Mutect2<br/>
    최종 실험에 사용된 돌연변이 분석 툴 Mutect2를 실행.<br/>
    24개로 분리된 염색체 bam file에 Variant Calling 과정을 24번을 수행해 최종 생식세포 돌연변이를 얻었다.
<br/>
  
방대한 데이터 분석을 위해 소요시간을 단축 시킨 variant calling(돌연변이 분석) 파이프라인을 구성하였다.

기존의 돌연변이 분석 툴인 Strelka2, Mutect2를 비교하여 실험을 진행하였으며,<br/>
하나의 전장유전체를 24개의 염색체로 분리하여 variant calling 과정을 병렬로 진행해 소요시간을 줄임.

## Post<br/>
<br/>

![슈퍼컴퓨터_유전체분석_포스터](https://user-images.githubusercontent.com/72204267/195063804-267dc7fa-3fae-462e-ab1d-209f620d86fe.jpg)
