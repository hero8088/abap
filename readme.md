### ABAP-PLATFORM-TRIAL 윈도우기준 셋팅방법
# 1. wsl2 설치
# 2. docker 설치
# 3. docker hub에서 abap-platform-trial 검색해서 다운받음
# 4.컨테이너 실행명령
# docker run -it `
-h vhcala4hci `
--name abap-trial `
--shm-size 8g `
--memory 14g `
--memory-swap 30g `
--sysctl kernel.shmmni=32768 `
--sysctl kernel.shmall=1073741824 `
--sysctl kernel.shmmax=8589934592 `
-p 30213:30213 `
-p 3200:3200 `
-p 3300:3300 `
-p 3900:3900 `
-p 8000:8000 `
-p 44300:44300 `
-v D:\abapData\A4H_Multiple.txt:/opt/sap/HDB_license `
toberic/abap-platform-trial:1909 `
-agree-to-sap-license `
-skip-limits-check
4-1. 컨테이너 실행 실패문제 : 메모리, 하드 (C:\Users\한종석\.wslconfig 파일셋팅)
5.라이센스 다운로드 : https://go.support.sap.com/minisap/#/minisap
5-1. A4H선택,  하드웨어키(처음 컨테이너 실행 시 라이센스문제 로그에 하드웨어키 나옴)

기타 명령어 모음
sapcontrol -nr 00 -function GetProcessList

HDB stop
HDB start

