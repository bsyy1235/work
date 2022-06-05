# 리눅스 명령어

### 1. top
 : 시스템의 프로세스/메모리 사용 상태를 5초 간격으로 업데이트하여 출력
 
 top명령어를 통해 서버의 CPU 사용량, 메모리 사용량 등을 확인할 수 있고, 서버에서 구독 중인 모든 어플리케이션들을 CPU 사용률이나 메모리 사용률이 많은 순서대로 나열하여 모니터링이 가능하다.
 
 + top 명령어 실행 후 명령어
  ![top](https://user-images.githubusercontent.com/105877750/172046340-1ebccaa3-7280-4c70-9dfd-769ee7e6054a.PNG)

>> 1: CPU 코어별 사용 현황
>> 
>> m: 메모리 사용률 시각화 표시
>> 
>> Shift + p: CPU 사용률이 높은 프로세스를 기준으로 나열
>>
>> Shift + m: 메모리 사용률이 높은 프로세스를 기준으로 나열
>>
>> Shift + t: 수행 시간이 긴 프로세스를 기준으로 나열
>>
>> u: 모니터링할 user를 선택하여, 해당 권한 프로세스 감시

+ 사용 옵션
 
 >> -b: 순간의 정보 확인할 수 있다
 >> 
 >> -n <숫자> : top 실행 주기를 <숫자>번 반복한다
 >>
 >> -d <숫자> : <숫자>초마다 정보가 갱신된다

### 2. ps
: 'process status'의 약자로, 프로세스의 현재 상태를 출력

ps: pid,cmd 등 프로세스의 기본적인 내용만 출력

+ 사용 옵션

>> -e: 모든 프로세스를 출력
>> 
>> -f: 풀 포맷으로 보여준다(uid,pid,ppid,TTY 등)
>> 
>> -l: 긴 포맷으로 보여준다 (풀 포맷+F,S,PRI 등의 정보를 더 보여줌)
>> 
>> -p <숫자>: 프로세스 번호가 <숫자>인 프로세스를 출력
>> 
>> -ef: 모든 프로세스를 풀 포맷으로 출력
>> 
>>  more 명령어를 이용하여 페이지 단위로 출력

***ps와 top의 차이점***

 -ps: ps한 시점에 proc에서 검색한 cpu 사용량 출력
 
 -top: proc에서 일정 주기로 합산해 cpu 사용률 출력


### 3. jobs
: 작업이 중지된 상태, 백그라운드로 진행 중인 작업 상태, 변경되었지만 보고되지 않은 상태 등을 표시

jobs[옵션][jobID]

jobs -x command[args]

+ 사용 옵션

>> -l: 프로세스 그룹 ID를 state 필드 앞에 출력
>> 
>> -n: 프로세스 그룹 중에 대표 프로세스 ID를 출력
>> 
>> -p: 각 프로세스 ID에 대해 한 행씩 출력
>> 
>> command: 지정한 명령어를 실행

+ *job 번호* [숫자]

중지되거나 백그라운드에서 돌고 싶은 작업이 있을 때 job번호를 앞단으로 가져와 실행

+ *jobs 기호*

" + " : 디폴트로 가장 먼저 가져와서 수행하게 될 프로세스(현재 실행 또는 실행 예정인 프로세스)

" - " : 현재 진행 중인 job이 끝나면 바로 다음에 수행될 프로세스

+ *jobs 명령어로 확인할 수 있는 세션의 상태값*

|상태|설명|
|----|----|
|Running|작업이 일시 중단되지 않았고 계속 진행 중임|
|Done|작업이 완료되어 0을 반환하고 종료했음|
|Done(code)|작업이 정상적으로 완료했으며, 0이 아닌 코드를 반환했음|
|Stopped|작업이 일시 중단됨|

### 4. kill
: 프로세스에 종료

kill [옵션] pid

kill 명령어는 시스템에 얘기치 않은 문제가 생긴 프로세스를 종료시킬 수 있다

ps명령어를 통해 종료하고 싶은 프로세스의 pid를 얻고 kill 명령어의 파라미터로 넘겨 실행하면 프로세스를 종료시킬 수 있다

+ 사용 옵션

>> pid: 종료시킬 프로세스 ID나 프로세스 이름을 지정
>> 
>> -s: 전달할 시그널 종류 지정, 시그널 이름이나 번호를 쓴다
>> 
>> -l: 시그널로 사용할 수 있는 이름들을 보여준다
>>
>> -1: -HUP 프로세스를 재활성화 
>>
>> -9: 프로세스 강제 종료

***

# vim 에디터 매크로 사용방법

> 녹화 q

> 실행 @
