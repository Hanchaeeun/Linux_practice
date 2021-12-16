# Linux_pratice
유전체 데이터 돌연변이 분석

# [수원대학교]슈퍼컴퓨터 유전체분석 연구
2021.04.01- 2021.10.31

## purpose
- 슈퍼컴퓨터 기반 유전체 변이분석 파이프 라인 최적화 기술 개발

## System environment
KISTI 슈퍼컴퓨터 5호기 누리온 (05-Nurion-KNL)
### OS
centOS 7
### Terminal program
MobaXterm

## assignment
- Linux 기초 활용 정리
- 유전체 데이터 분석에 대한 이해
  - 유전체 분석 도구 사용법
  - linux 활용 스크립트 구현
- PBS(스케줄러)를 이용한 작업 실행(Nurion)
- 슈퍼컴퓨터에 최적화된 Multi-threading 변이분석 파이프라인 구축
## create scripts
1. Setting the environment
 
    anaconda3에 python3.8 가상환경 생성 후 접속해 bwa툴 다운로드 
  
2. sampling  bam

    bamfile을 입력 받아 크기를 10%~100%로 랜덤 추출한 bam파일 출력
  
3. Strelka2
 
    돌연변이 분석 툴인 Strelka2를 설치 후 germline, somatic calling 후 변이파일(vcf) 출력
4. Mutect2 

    최종 실험에 사용된 돌연변이 분석 툴 Mutect2를 실행. 
    24개로 분리된 염색체 bam file에 variant calling과정을 24번을 수행.
    총 24개의 vcf파일을 얻는다.
