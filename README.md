# 밀크찬 도시능력자 서버팩 | Release
> 도시능력자 플러그인은 [새벽](https://github.com/Daybreak365/AbilityWar)님이 제작했습니다.
> 추가기능을 개발한 밀크찬은 [AbilityWars](https://github.com/Daybreak365/AbilityWar)의 [라이선스](https://github.com/Daybreak365/AbilityWar/blob/master/LICENSE.md)를 지킵니다.

## 서버 필수 사양
- Windows 혹은 마인크래프트 서버를 구동할수 있는 운영체제
- JAVA 17 이상 사용자

## 서버 사용법

### 윈도우 사용자용
1. 릴리즈된 것중 _windows.zip 버전을 다운로드
2. 해당 압축파일을 원하는 위치에 압축해제후 start.bat 파일 실행

- 해당 start.bat 에는 아래와 같은 인수가 담겨있음. [Aikar's Flags](https://docs.papermc.io/paper/aikars-flags)
```cmd
@echo off
chcp 65001 >nul
:123
java -Xms4G -Xmx16G -XX:+IgnoreUnrecognizedVMOptions -XX:+UseG1GC -XX:+ParallelRefProcEnabled -XX:MaxGCPauseMillis=200 -XX:+UnlockExperimentalVMOptions -XX:+DisableExplicitGC -XX:+AlwaysPreTouch -XX:G1HeapWastePercent=5 -XX:G1MixedGCCountTarget=4 -XX:G1MixedGCLiveThresholdPercent=90 -XX:G1RSetUpdatingPauseTimePercent=5 -XX:SurvivorRatio=32 -XX:+PerfDisableSharedMem -XX:MaxTenuringThreshold=1 -XX:G1NewSizePercent=30 -XX:G1MaxNewSizePercent=40 -XX:G1HeapRegionSize=8M -XX:G1ReservePercent=20 -XX:InitiatingHeapOccupancyPercent=15 -Dusing.aikars.flags=https://mcflags.emc.gs/ -Daikars.new.flags=true -jar server.jar nogui
pause
goto 123
```
- 기본값은 **최소 4기가/최대 16G**로 설정되어있음 원하는만큼 변경 가능


### 리눅스 사용자용
1. 릴리즈된 것중 _linux.tar 버전 다운로드
2. 원하는 위치에 압축 해제후 해당 폴더에서 터미널 실행
3. 아래 명령어 입력
```bash
chmod +x start.sh
```

4. 이후 아래 명령어 실행시 서버 오픈
```bash
./start.sh
```

## 기본적인 능력자 전쟁 명령어 목록:
- /aw start -> 관리자만이 사용할 수 있는 능력자 시작 명령어입니다. | aliases: /게임시작, /ability start
- /aw stop -> 관리자만이 사용할 수 있는 능력자 종료 명령어입니다. | aliases: /ability stop
- /aw config game -> 관리자만이 컨트롤할 수 있는 게임 관련 설정 명령어입니다. | aliases: /ability config game
- /aw gamemode -> 관리자만 사용할 수 있는 믹스 혹은 다른모드에 관한 설정입니다.
- /aw util spec <닉네임> -> 해당 유저를 게임에 참가하지 않는 관전자 상태로 변경합니다.
- /aw util inv <시간(초)> -> 시간(초) 로 무적시간을 변경합니다.
- /aw util check <닉네임> -> 해당 유저의 능력을 확인합니다.
- /aw util abi <닉네임> <능력> -> 해당 유저에게 능력을 강제로 할당합니다. (@a 사용 가능)
- /aw config blacklist <능력> -> 해당 능력을 능력추첨에서 제외합니다.
- /aw check -> 자신에게 할당된 능력을 확인합니다.
- /aw yes|no -> 자신에게 할당된 능력을 거절 혹은 확정합니다.

## 밀크찬이 추가한 능력자 전쟁 관련 기능&명령어
### 기능목록
- 개인전에서 마지막 1인이 생존했을때 우승 메시지를 자동으로 띄우고 5초후 초기화작업을 시작합니다.
- 월드보더를 시작하면 월드보더가 특정 시간을 기준점으로 자동으로 줄어듭니다.
- 초기화 -> 모든 유저를 무적으로 변경/월드보더 자동으로 중지/서버에 모든 엔티티 제거/모든 유저 서바이벌 설정/도시능력자 맵 초기화... 등등

### 명령어
- /시작 <학교|대저택> -> 기능 2번과 같이 원하는곳을 중앙으로 월드보더를 시작하며 초반 3분이후 자동으로 줄어듭니다.
- /중지 -> /시작으로 월드보더를 시작했을때 월드보더를 중지할수 있습니다.
- /초기화 -> 기능 3번에 초기화작업이 시작됩니다.
- /칭호설정 <스트리머|관리자|유저> <닉네임> -> 스트리머 혹은 관리자 혹은 유저(기본값) 칭호를 특정 유저에게 적용합니다. (서버에 접속한 기록이 있는유저만 적용가능)
- /능력목록 -> 능력자 전쟁에 있는 모든 능력을 확인할수 있습니다.
- /능력확인 -> aw check 를 한글화 하였습니다.
- /능력수락 -> 할당된 능력을 수락할 수 있습니다.
- /능력거절 -> 할당된 능력을 거절할 수 있습니다.
- /능력정보 <능력이름> -> 능력이름의 정보를 확인할 수 있습니다.
- /게임시작 -> 능력자 게임을 시작합니다.
- /팀챗토글 -> 팀전 설정시 팀챗을 토글할 수 있습니다.

## 플러그인 목록
- EssentialsX/EssentialsXspawn/EssentialsXchat
  - 편리를 위한 플러그인 및 스폰위치 지정, 칭호설정을 위한 플러그인
- Luckperms
  - 자동완성 필터링 혹은 권한설정 및 칭호를 위한 플러그인
- GrimAC
  - 사용해본것중 도시능력자에서 가장 오탐지가 없는 안티치트
- WorldEdit/WorldGuard
  - 월드의 Y좌표 제한 및 스폰의 블럭이 부숴지지 않게 설정하는 플러그인
- AbilityWars
  - 도시능력자에서 메인 플러그인
- HidePlugins
  - 플러그인 목록을 가려서 서버의 보안을 강화할수 있음
- Vault
  - 칭호를 사용하기위한 이코노미 플러그인
- Spark
  - 서버 TPS 를 더욱 효율적으로 확인하기 위한 플러그인
- Skript,Sk-Reflect,Sk-RayFall,Sk-Query,Sk-Bee,Sk-ellett
  - 초기화 및 월드보더 등 밀크찬의 추가 기능을 사용하기 위한 플러그인
- MultiVerse
  - 월드 초기화를 위한 멀티 월드 플러그인.
- milkchan-api-1.20.4
  - 1.20.x 버전을 위해 따로 빌드한 PVP (on|off) 기능을 가지고있는 플러그인
- CompleteFilter
  - 유저들의 자동완성을 커스텀해서 서버의 어떠한 플러그인이 있는지 확인 불가능하게 함
- CoreProtect
  - 월드 리셋시 사용 (현재는 별로 필요없음)
- MOTD
  - 서버의 motd를 수정하는 플러그인 (설정파일 건들지 말기!!!!)
- ProtocolLib
  - 서버의 플러그인의 호환성을 높이는 플러그인
