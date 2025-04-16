# Azure AI Service Test

## 1. 작업환경 설정

1.	Python 3.11.6 설치([다운로드](https://www.python.org/ftp/python/3.11.6/python-3.11.6-amd64.exe))
    -	Python(이하 파이썬)은 직관적이고 간결한 문법으로, 프로그래머들은 물론 비전공자들 사이에서도 최근 가장 주목받는 언어입니다. 본 과정에서는Azure Function구성을 위해 설치를 진행합니다.

2.	VSCode 작업 Tool([다운로드](https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user))
    -	VS Code는 거의 모든 주요 프로그래밍 언어를 지원합니다. JavaScript, TypeScript, CSS, HTML과 같이 여러 언어가 기본으로 제공되지만, 다른 언어의 확장 기능은 VS Code Marketplace에서 찾을 수 있습니다.
    -	버전 : VSCodeUserSetup-x64-1.96.4
    
## install library
```shell
pip install azure-ai-textanalytics==5.3.0
pip install azure-identity
```

## Azure Managed Identity
Azure VM에 Managed Identity(MI)를 사용하여 Azure Cognitive Services (AI Service)와 연동하려면 Managed Identity에 적절한 권한을 부여해야 합니다. Managed Identity를 통해 Azure Cognitive Services에 액세스하려면 Azure Role-Based Access Control (RBAC) 역할을 설정해야 합니다.

아래는 Managed Identity를 설정하고 AI Service에 필요한 권한을 부여하는 단계입니다:
 

### 1. Azure VM에 Managed Identity 활성화

먼저 Azure VM에 시스템 할당된 Managed Identity(System-assigned Managed Identity)를 활성화하거나, 사용자 할당된 Managed Identity(User-assigned Managed Identity)를 연결해야 합니다.

1. Azure Portal에서 Managed Identity 활성화
   
    Azure Portal에서 VM 리소스를 엽니다.
    왼쪽 메뉴에서 Identity를 선택합니다.
    System-assigned 탭으로 이동하여 On으로 전환합니다.
    저장을 클릭합니다.
    활성화되면 VM의 시스템 할당된 Managed Identity가 생성됩니다.
   
2. 사용자 할당된 Managed Identity 연결 (선택사항)

    사용자 할당된 Managed Identity를 사용하려면:
    Azure Portal에서 Managed Identity를 새로 생성합니다.
    생성된 Managed Identity를 VM에 할당합니다:
    VM → Identity → User-assigned 탭으로 이동하여 추가(Add)합니다.
 

### 2. AI Service에 권한 부여

    Managed Identity가 Azure Cognitive Services(AI Service)에 액세스하려면 적절한 Azure RBAC 역할을 부여해야 합니다.

1. 권한 부여를 위한 역할

Azure Cognitive Services 리소스에 적합한 권한은 다음과 같습니다:
- Cognitive Services User: Cognitive Services API를 호출할 수 있는 권한을 제공합니다.
- Cognitive Services Contributor (더 높은 권한): Cognitive Services 리소스의 관리 및 호출 권한을 제공합니다.

일반적으로 API 호출만 필요하다면 Cognitive Services User 역할이면 충분합니다.

2. 권한 부여 방법

Azure Portal에서 Azure Cognitive Services 리소스를 엽니다.
왼쪽 메뉴에서 **Access control (IAM)**을 선택합니다.
Add role assignment를 클릭합니다.
역할(Role)에서 Cognitive Services User를 선택합니다.
Assign access to에서 Managed Identity를 선택합니다.
Select members에서 VM의 Managed Identity를 검색하여 선택합니다.
저장을 클릭합니다.