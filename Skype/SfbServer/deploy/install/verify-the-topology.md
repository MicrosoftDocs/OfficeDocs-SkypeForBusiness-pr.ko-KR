---
title: 비즈니스용 Skype 서버 토폴로지 확인
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '요약: 비즈니스용 Skype 서버 토폴로지 및 Active Directory 서버가 예상대로 작동하는지 확인하는 방법을 알아봅니다.'
ms.openlocfilehash: ec63977f4c70845f39aafe3521591ec93777f7d5
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860549"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>비즈니스용 Skype 서버 토폴로지 확인
 
**요약:** 비즈니스용 Skype 서버 토폴로지 및 Active Directory 서버가 예상대로 작동하는지 확인하는 방법을 알아봅니다.
  
토폴로지와 토폴로지의 각 서버에 비즈니스용 Skype 서버 시스템 구성 요소가 설치되면 토폴로지가 예상대로 작동하는지 확인할 준비가 된 것입니다. 여기에는 전체 도메인이 도메인에서 사용할 수 있는 비즈니스용 Skype 알 수 있도록 구성이 모든 Active Directory 서버로 전파되었는지 확인하는 작업이 포함됩니다. 1~5단계는 순서대로 수행할 수 있습니다. 그러나 다이어그램에 설명된 대로 6단계, 7, 8단계를 순서대로, 1~5단계 후에 수행해야 합니다. 토폴로지 확인은 8/8단계입니다.
  
![개요 다이어그램.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>프런트 엔드 풀 배포 테스트

마지막 단계는 프런트 엔드 풀을 테스트하고 비즈니스용 Skype 클라이언트가 서로 통신할 수 있는지 확인하는 것입니다. 
  
### <a name="add-users-and-verify-client-connectivity"></a>사용자 추가 및 클라이언트 연결 확인

1. Active Directory 컴퓨터 및 사용자를 사용하여 비즈니스용 Skype 서버 배포(비즈니스용 Skype 서버 제어판 설치됨)에 대한 관리자 역할의 Active Directory 사용자 개체를 **CSAdministrator** 그룹에 추가합니다.
    
    > [!IMPORTANT]
    > CsAdministors 그룹에 적절한 사용자 및 그룹을 추가하지 않으면 "권한 없음: RBAC(역할 기반 액세스 제어) 권한 부여 실패로 인해 액세스가 거부됨"이라는 비즈니스용 Skype 서버 제어판 열 때 오류가 발생합니다. 
  
2. 사용자 개체가 현재 로그온되어 있는 경우 로그오프하고 다시 로그온하여 새 그룹 지정을 등록합니다.
    
    > [!NOTE]
    > 사용자 계정은 비즈니스용 Skype 서버 실행하는 서버의 로컬 관리자가 될 수 없습니다. 
  
3. 관리 계정을 사용하여 비즈니스용 Skype 서버 제어판 설치된 컴퓨터에 로그온합니다.
    
4. 비즈니스용 Skype 서버 제어판 시작한 다음 메시지가 표시되면 자격 증명을 제공합니다. 비즈니스용 Skype 서버 제어판 배포 정보를 표시합니다.
    
5. 왼쪽 탐색 모음에서 **토폴로지( Topology**)를 클릭한 다음 서비스 상태에 녹색 화살표가 있는 컴퓨터가 표시되고 복제 상태에 대한 녹색 확인 표시가 배포되고 온라인 상태가 된 각 비즈니스용 Skype 서버 역할 옆에 있는지 확인합니다. 
    
6. 왼쪽 탐색 표시줄에서 **사용자** 및 **사용자 사용** 을 차례로 클릭합니다. 
    
7. **새 비즈니스용 Skype 서버 사용자** 페이지에서 **추가** 를 클릭합니다.
    
8. 찾을 개체에 대한 검색 매개 변수를 정의하려면 **Active Directory에서 선택** 페이지에서 **검색** 을 선택하고 경우에 따라 **필터 추가** 를 클릭하면 됩니다. **LDAP 검색** 을 선택하고 LDAP 식을 입력하여 반환되는 개체를 필터링하거나 제한할 수도 있습니다. 검색 옵션을 결정한 후 **찾기** 를 클릭합니다.
    
9. 검색 결과 창에서 추가할 사용자를 선택한 다음 **확인을** 클릭합니다.
    
10. **새 비즈니스용 Skype 서버 사용자** 페이지에서 선택한 사용자가 **사용자** 표시에 있습니다. 풀 목록에 **사용자 할당 목록에서 사용자가** 상주해야 하는 서버를 선택합니다.
    
    다음은 개체를 구성하는 데 사용할 수 있는 옵션 목록입니다.
    
    - **사용자의 SIP URI 생성**
    
    - **전화**
    
    - **줄 URI**
    
    - **회의 정책**
    
    - **클라이언트 버전 정책**
    
    - **PIN 정책**
    
    - **외부 액세스 정책**
    
    - **보관 정책**
    
    - **위치 정책**
    
    - **클라이언트 정책**
    
    기본 기능을 테스트하려면 **사용자 SIP URI 생성** 설정(구성의 다른 옵션은 기본 설정을 사용함)에 원하는 옵션을 선택한 다음 그림과 같이 **[사용]** 을 클릭합니다.
    
     ![제어판 사용자를 사용하도록 설정합니다.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. **사용** 열에 사용자가 설정되어 있음을 나타내는 확인 표시가 표시된 요약 페이지가 표시됩니다. **SIP 주소** 열에 사용자 로그인 구성에 필요한 주소가 표시됩니다.
    
     ![사용자가 비즈니스용 Skype 서버 제어판 추가되었습니다.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. 한 사용자를 도메인에 가입된 컴퓨터에 로그온하고 다른 사용자를 도메인의 다른 컴퓨터에 로그온합니다.
    
13. 두 클라이언트 컴퓨터 각각에 비즈니스용 Skype 클라이언트를 설치한 다음 두 사용자가 비즈니스용 Skype 서버 로그인하여 서로 인스턴트 메시지를 보낼 수 있는지 확인합니다.
    

