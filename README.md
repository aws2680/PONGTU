# PONGTU
pongtu
# KKuTu
- Made by [JJoriping](http://blog.jjo.kr/)
- Special thanks to
	* [샌드박스 :: SDBX](http://cafe.naver.com/sdbx)
	* [SWMaestro](http://www.swmaestro.kr)
	* You to have interested in this repository :)
- [KKuTu Wiki](https://github.com/JJoriping/KKuTu/wiki)
- [프리 서버 목록](http://jjo.kr/kkutu)
- Languages
	* [English](#english)
	* [한국어](#한국어)

## English
> Rule the words! KKuTu Online

**KKuTu** is a casual game containing various word games that let players use their vocabulary.
Players can play alone with a robot, or play with other players who have entered to a server.
This repository provides you what you have to prepare to play **KKuTu**.

### KKuTu Client
- *Not implemented*
- But you can connect to a server via your web browser if you know an address of the server!

### KKuTu Server
#### For Windows
1. Download or clone this repository to your machine.
1. Install [node.js](https://nodejs.org/en/) and npm(this will be installed automatically).
1. Install [PostgreSQL](https://www.postgresql.org/) database server and pgAdmin(this will be installed automatically).
1. Run pgAdmin and put the SQL file(`./db.sql`) into your database.
	* For further details, visit [my blog][dev-blog].
1. Run the batch file(`./server-setup.bat`).
1. Run the batch file(`./Server/run.bat`).
	* If you want to close the server, it is recommended that closing not the command prompt window, but the window generated by the command.

#### For Linux
1. Download or clone this repository to your machine.
1. Install *node.js* and *npm* via a package manager.
1. Install *PostgreSQL* database server via a package manager.
1. Put the SQL file(`./db.sql`) into your database.
	1. Run a command like: `sudo -u postgres psql --quiet main < ./db.sql`
1. Run the shell script file(`./server-setup.bat`). (It is a bat file for Windows but it will also work on Linux.)
1. Run these on working directory `./Server`:
	1. (Web server) `node lib/Web/cluster.js 1`
	1. (Game server) `node lib/Game/cluster.js 0 1`

#### Common
- This repository contains some data from [WordNet](https://wordnet.princeton.edu/). Please provide users the license of WordNet when you operate this server.
- You should edit the file(`./Server/lib/sub/global.json`) to connect to your PostgreSQL database server.
- The host `127.0.0.2` is reserved for connections between your web server and game server.
- Once the server is successfully installed, you can do just the last step of above-mentioned guideline whenever you want to run the server.
- You can open a browser and go to `127.0.0.1`(or external IP address for other people) to play **KKuTu**.
- Ranking and some session features require [Redis](https://redis.io/) server. This is optional.
- If you use Cloudflare, you should set status of DNS Tab to 'DNS only'. 'DNS and HTTP proxy (CDN)' status is the reason of unable to open and enter the room.

#### License
- [GNU General Public License](https://github.com/JJoriping/KKuTu/blob/master/LICENSE) for all source codes in this repository.
- [Creative Commons License CC BY](https://creativecommons.org/licenses/by/4.0/) for all images and sounds in this repository.
	- But if you use these for operating KKuTu service provided by this repository, you may omit the attribution(BY).

## 한국어
> 글자로 놀자! 끄투 온라인

**끄투**는 여러분의 어휘력을 발휘할 수 있는 다양한 단어 게임들이 모여 있는 캐주얼 게임입니다.
로봇과 혼자서 게임을 할 수도 있고, 서버에 접속해 있는 다른 사람들과 함께 할 수도 있죠.
이 저장소는 여러분이 **끄투**를 즐기기 위해 준비해야 할 것들에 대해 알리고 있습니다.

### 끄투 클라이언트
- *구현되지 않음*
- 하지만 접속할 서버의 주소를 알고 있다면 웹 브라우저를 이용하여 서버에 접속할 수 있습니다!

### 끄투 서버
#### Windows 전용
1. 이 레포지토리를 내려받습니다.
1. [node.js](https://nodejs.org/ko/) 인스톨러를 내려받아 npm(자동으로 설치됨)과 함께 설치합니다.
1. [PostgreSQL](https://www.postgresql.org/) 인스톨러를 내려받아 pgAdmin(자동으로 설치됨)과 함께 설치합니다.
1. pgAdmin을 실행시키고 SQL 파일(`./db.sql`)을 데이터베이스에 입력시킵니다.
	* 자세한 과정은 [개발자 블로그][dev-blog]를 참고하세요.
1. 배치 파일(`./server-setup.bat`)을 실행시킵니다.
1. 배치 파일(`./Server/run.bat`)을 실행시킵니다.
	* 되도록 이 배치 파일을 직접 종료하지 말고 이를 실행시켜 나타나는 창을 종료하세요.

#### Linux 전용
1. 이 레포지토리를 내려받습니다.
1. 패키지 매니저를 이용하여 *node.js*와 *npm*을 설치합니다.
1. 패키지 매니저를 이용하여 *PostgreSQL*과 *psql*을 설치합니다.
1. SQL 파일(`./db.sql`)을 데이터베이스에 입력시킵니다.
	1. 명령어를 다음 예와 같이 입력할 수 있습니다: `sudo -u postgres psql --quite main < ./db.sql`
1. 섈 스크립트 파일(`./server-setup.bat`)을 실행시킵니다. (Windows 전용 파일이지만 Linux에서도 작동합니다.)
1. 경로 `./Server`에서 다음 명령어들을 실행합니다:
	1. (웹 서버) `node lib/Web/cluster.js 1`
	1. (게임 서버) `node lib/Game/cluster.js 0 1`

#### 공통
- 본 레포지토리에는 [WordNet](https://wordnet.princeton.edu/) 자료가 포함되어 있습니다. 서버를 운영할 때 반드시 사용자에게 이에 대한 라이선스를 안내해야 합니다.
- PostgreSQL 데이터베이스 서버에 접속하기 위해서는 설정 파일(`./Server/lib/sub/global.json`)에서 `PG_PASS` 값을 수정해야 합니다.
- 호스트 `127.0.0.2`는 웹 서버와 게임 서버 사이의 연결을 위해 예약된 주소이므로 이 주소를 사용하지 말아야 합니다.
- 서버가 정상적으로 설치된 다음부터는 서버를 실행시키기 위해서 가장 마지막 단계만 수행하면 됩니다.
- 서버가 성공적으로 열린 후 웹 브라우저에서 `127.0.0.1`(다른 사람들은 해당 컴퓨터의 외부 IP 주소)로 접속하여 끄투를 즐길 수 있습니다.
- 랭킹 및 세션 기능 일부는 [Redis](https://redis.io/) 서버가 실행되어야만 작동합니다. 일단 이를 설치하지 않아도 서버가 작동할 수 있도록 조치했습니다.
- 클라우드 플레어를 사용하신다면, DNS 탭의 status를 DNS only로 두세요. DNS and HTTP proxy (CDN)으로 둘 경우, 방 만들기와 방 입장이 되지 않습니다.

#### 라이선스
- 모든 소스 코드에 대해: [GNU 일반 공중 사용 라이선스](https://github.com/JJoriping/KKuTu/blob/master/LICENSE)
- 모든 이미지 및 소리에 대해: [크리에이티브 커먼즈 라이선스 CC BY](https://creativecommons.org/licenses/by/4.0/)
	- 다만 본 레포지토리에서 제공하는 소스 코드로 끄투 서비스를 운영하기 위해 이들을 사용하는 경우 저작자 표시(BY)를 생략할 수 있습니다.

[dev-blog]: http://blog.jjo.kr/220935346136
