# Azure AI Service Test
## 1. 작업환경 설정
1.	Azure CLI 설치([다운로드](https://aka.ms/installazurecliwindowsx64))
o	Azure CLI는 Windows, macOS 및 Linux 환경에 설치할 수 있습니다. Docker 컨테이너와 Azure Cloud Shell에서도 실행할 수 있습니다.
o	버전 : 2.44.1

2.	Git 설치([다운로드](https://github.com/git-for-windows/git/releases/download/v2.47.1.windows.1/Git-2.47.1-64-bit.exe))
o	Git은 빠르고 효율적으로 작은 프로젝트부터 대규모 프로젝트까지 모든 것을 처리하도록 설계된 무료 오픈 소스 분산형 버전 제어 시스템입니다.
o	버전 : 2.40.0.windows.1

3.	Python 3.10 설치([다운로드](https://www.python.org/ftp/python/3.10.11/python-3.10.11-amd64.exe))
3.	Python 3.11 설치([다운로드](https://www.python.org/ftp/python/3.11.6/python-3.11.6-amd64.exe))
o	Python(이하 파이썬)은 직관적이고 간결한 문법으로, 프로그래머들은 물론 비전공자들 사이에서도 최근 가장 주목받는 언어입니다. 본 과정에서는Azure Function구성을 위해 설치를 진행합니다.

4.	VSCode 작업 Tool([다운로드](https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user))
o	VS Code는 거의 모든 주요 프로그래밍 언어를 지원합니다. JavaScript, TypeScript, CSS, HTML과 같이 여러 언어가 기본으로 제공되지만, 다른 언어의 확장 기능은 VS Code Marketplace에서 찾을 수 있습니다.
o	버전 : VSCodeUserSetup-x64-1.96.4
o	다운로드 후 아래 과정 진행
1.	설치 후 az login을 통해 연동 
2.	Azure Tools Extensions 설치 및
3.	Python Extensions 설치

5.	Azure Function Core Tools 설치([다운로드](https://go.microsoft.com/fwlink/?linkid=2174087))
o	Azure Functions Core Tools를 사용하여 로컬 머신에서 함수를 개발하고 테스트할 수 있습니다. 
o	버전 : v4.x - Windows 64비트(권장. Visual Studio Code 디버깅에는 64비트가 필요)
