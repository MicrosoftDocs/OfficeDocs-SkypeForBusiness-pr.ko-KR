---
title: 사용자 계정에서 토폴로지 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '요약: 비즈니스용 Skype 서버 Active Directory 서버가 예상대로 작동하고 있는지 확인하는 방법을 설명하는 방법을 제공합니다. Microsoft 평가판 센터에서 비즈니스용 Skype 서버 평가판을 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 다운로드합니다.'
ms.openlocfilehash: 743741fd18766116ed923a2af632f33c88343ef5957a84165edc7702b3b6593f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294775"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>사용자 계정에서 토폴로지 비즈니스용 Skype 서버
 
**요약:** 토폴로지 및 Active Directory 비즈니스용 Skype 서버 예상대로 작동하고 있는지 확인하는 방법을 알아보십시오. Microsoft 평가판 비즈니스용 Skype 서버 [평가판을 다운로드합니다.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
토폴로지 및 비즈니스용 Skype 서버 시스템 구성 요소를 토폴로지의 각 서버에 설치한 후 토폴로지가 예상대로 작동하고 있는지 확인할 준비가 된 것입니다. 여기에는 구성이 모든 Active Directory 서버로 전파되어 전체 도메인이 도메인에서 사용할 수 비즈니스용 Skype 수 있는지 확인하는 것이 포함됩니다. 1~5단계는 순서에 따라 수행하면 됩니다. 그러나 다이어그램에 설명된대로 1~5단계를 순서대로 6, 7, 8단계를 순서대로 수행해야 합니다. 토폴로지 확인은 8단계 중 8단계입니다.
  
![개요 다이어그램.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>프런트 엔드 풀 배포 테스트

마지막 단계는 프런트 엔드 풀을 테스트하고 클라이언트가 서로 통신할 비즈니스용 Skype 확인하는 것입니다. 
  
### <a name="add-users-and-verify-client-connectivity"></a>사용자 추가 및 클라이언트 연결 확인

1. Active Directory 컴퓨터 및 사용자를 사용하여 비즈니스용 Skype 서버 배포(비즈니스용 Skype 서버 제어판이 설치된)에 대한 관리자 역할의 Active Directory 사용자 개체를 **CSAdministrator** 그룹에 추가합니다.
    
    > [!IMPORTANT]
    > CsAdministors 그룹에 적절한 사용자 및 그룹을 추가하지 않는 경우 "권한이 부여되지 않은 경우 RBAC(역할 기반 액세스 제어) 권한 부여 실패로 인해 액세스가 거부됩니다비즈니스용 Skype 서버 제어판을 열면 오류가 발생합니다. 
  
2. 사용자 개체가 현재 로그온되어 있는 경우 로그오프하고 다시 로그온하여 새 그룹 지정을 등록합니다.
    
    > [!NOTE]
    > 사용자 계정은 사용자 계정을 실행 중인 서버의 로컬 관리자일 비즈니스용 Skype 서버. 
  
3. 관리 계정을 사용하여 제어판이 설치된 비즈니스용 Skype 서버 로그온합니다.
    
4. 제어 비즈니스용 Skype 서버 시작한 다음 메시지가 표시될 경우 자격 증명을 제공합니다. 비즈니스용 Skype 서버 제어판에 배포 정보가 표시됩니다.
    
5. 왼쪽 탐색 모음에서 토폴로지 를 클릭하고 서비스 상태에 녹색 화살표가 있는 컴퓨터가 표시되고 복제 상태에 대한 녹색 확인 표시가 배포되고 온라인 상태인 각 비즈니스용 Skype 서버 역할 옆에 있는지 확인합니다. 
    
6. 왼쪽 탐색 표시줄에서 **사용자** 및 **사용자 사용** 을 차례로 클릭합니다. 
    
7. 새 사용자 **비즈니스용 Skype 서버 페이지에서** 추가를 **클릭합니다.**
    
8. 찾을 개체에 대한 검색 매개 변수를 정의하려면 **Active Directory에서 선택** 페이지에서 **검색** 을 선택하고 경우에 따라 **필터 추가** 를 클릭하면 됩니다. **LDAP 검색** 을 선택하고 LDAP 식을 입력하여 반환되는 개체를 필터링하거나 제한할 수도 있습니다. 검색 옵션을 결정한 후 찾기를 **클릭합니다.**
    
9. 검색 결과 창에서 추가할 사용자를 선택하고 확인 을 **클릭합니다.**
    
10. 새 **비즈니스용 Skype 서버 사용자** 페이지에 선택한 사용자가 **사용자 표시에** 표시됩니다. 풀에 **사용자 할당 목록에서** 사용자가 상주해야 하는 서버를 선택합니다.
    
    다음은 개체를 구성하는 데 사용할 수 있는 옵션 목록입니다.
    
    - **사용자의 SIP URI 생성**
    
    - **전화 통신**
    
    - **줄 URI**
    
    - **회의 정책**
    
    - **클라이언트 버전 정책**
    
    - **PIN 정책**
    
    - **외부 액세스 정책**
    
    - **보관 정책**
    
    - **위치 정책**
    
    - **클라이언트 정책**
    
    기본 기능을 테스트하려면 사용자의 **SIP URI** 생성 설정에 대해 원하는 옵션(구성의 다른 옵션은 기본 설정을 사용)을 선택한 다음 그림과 같이 사용을 클릭합니다.
    
     ![제어판에서 사용자를 사용하도록 설정](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. 사용 열에 사용자가 설정되어 있는 것을  나타내는 확인 표시를 표시하는 요약 페이지가 표시됩니다. **SIP 주소** 열에 사용자 로그인 구성에 필요한 주소가 표시됩니다.
    
     ![제어판에 비즈니스용 Skype 서버 추가된 사용자입니다.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. 도메인에 가입된 컴퓨터에 한 사용자를 로그온하고 다른 사용자는 도메인의 다른 컴퓨터에 로그온합니다.
    
13. 두 비즈니스용 Skype 각각에 클라이언트 클라이언트를 설치한 다음 두 사용자가 모두 클라이언트에 로그인하여 인스턴트 비즈니스용 Skype 서버 수 있는지 확인하고 서로에게 인스턴트 메시지를 보낼 수 있는지를 확인해야 합니다.
    

