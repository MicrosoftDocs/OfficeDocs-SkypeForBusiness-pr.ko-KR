---
title: 비즈니스용 Skype 서버에서 토폴로지 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: '요약: 비즈니스용 Skype 서버 토폴로지와 Active Directory 서버가 예상 대로 작동 하는지 확인 하는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: 6c7d7a67cab2cbd383ee26eb64f478985bcc4b27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245517"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 토폴로지 확인
 
**요약:** 비즈니스용 Skype 서버 토폴로지와 Active Directory 서버가 예상 대로 작동 하는지 확인 하는 방법에 대해 알아봅니다. [Microsoft 평가 센터](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)에서 비즈니스용 Skype 서버의 무료 평가판을 다운로드 하세요.
  
토폴로지가 게시 되 고 토폴로지의 각 서버에 비즈니스용 Skype 서버 시스템 구성 요소가 설치 된 후 토폴로지가 예상 대로 작동 하는지 확인할 준비가 되었습니다. 여기에는 전체 도메인이 도메인에서 비즈니스용 Skype를 사용할 수 있도록 모든 Active Directory 서버로 구성이 전파 되었음을 확인 하는 것이 포함 됩니다. 1 ~ 5 단계는 순서에 관계 없이 수행할 수 있습니다. 그러나 6, 7, 8 단계를 순서 대로 수행 하 고 다이어그램에 명시 된 대로 1 ~ 5 단계를 완료 해야 합니다. 토폴로지 확인은 8 단계입니다.
  
![개요 다이어그램.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>프런트 엔드 풀 배포 테스트

마지막 단계는 프런트 엔드 풀을 테스트 하 고 비즈니스용 Skype 클라이언트가 서로 통신할 수 있는지 확인 하는 것입니다. 
  
### <a name="add-users-and-verify-client-connectivity"></a>사용자 추가 및 클라이언트 연결 확인

1. Active Directory 컴퓨터 및 사용자를 사용 하 여 비즈니스용 Skype 서버 배포에 대 한 관리자 역할의 Active Directory 사용자 개체 (비즈니스용 Skype Server 제어판이 설치 되어 있는 경우)를 **csadministrator** 그룹에 추가 합니다.
    
    > [!IMPORTANT]
    > CsAdministors 그룹에 적절 한 사용자 및 그룹을 추가 하지 않으면 "권한이 없음: 역할 기반 액세스 제어 (RBAC) 권한 부여 오류로 인해 액세스가 거부 됨을 나타내는 비즈니스용 Skype 서버 제어판을 열 때 오류가 표시 됩니다. ." 
  
2. 사용자 개체가 현재 로그온 되어 있으면 로그 오프 한 다음 다시 로그온 하 여 새 그룹 할당을 등록 합니다.
    
    > [!NOTE]
    > 사용자 계정은 비즈니스용 Skype 서버를 실행 하는 서버의 로컬 관리자가 될 수 없습니다. 
  
3. 관리 계정을 사용 하 여 비즈니스용 Skype 서버 제어판이 설치 되어 있는 컴퓨터에 로그온 합니다.
    
4. 비즈니스용 Skype Server 제어판을 시작 하 고 메시지가 표시 되 면 자격 증명을 제공 합니다. 비즈니스용 Skype Server 제어판에 배포 정보가 표시 됩니다.
    
5. 왼쪽 탐색 모음에서 **토폴로지**를 클릭 한 다음 서비스 상태가 녹색 화살표가 있는 컴퓨터를 표시 하 고 복제 상태에 대 한 녹색 확인 표시가 배포 되어 온라인 상태가 된 각 비즈니스용 Skype 서버 역할 옆에 있는지 확인 합니다. 
    
6. 왼쪽 탐색 모음에서 **사용자**를 클릭 한 다음 **사용자 사용**을 클릭 합니다. 
    
7. **새 비즈니스용 Skype 서버 사용자** 페이지에서 **추가**를 클릭 합니다.
    
8. 찾으려는 개체에 대 한 검색 매개 변수를 정의 하려면 **Active Directory에서 선택** 페이지에서 **검색**을 선택한 다음 필요에 따라 **필터 추가**를 클릭할 수 있습니다. **Ldap 검색** 을 선택 하 고 ldap 식을 입력 하 여 반환 되는 개체를 필터링 하거나 제한할 수도 있습니다. 검색 옵션을 결정 한 후 **찾기를**클릭 합니다.
    
9. 검색 결과 창에서 추가 하려는 사용자를 선택한 다음 **확인**을 클릭 합니다.
    
10. **새 비즈니스용 Skype Server 사용자** 페이지에서 선택한 사용자가 **사용자에 게** 표시 됩니다. **풀에 사용자 할당** 목록에서 사용자가 상주해 야 하는 서버를 선택 합니다.
    
    다음은 개체를 구성 하는 데 사용할 수 있는 옵션의 목록입니다.
    
    - **사용자의 SIP URI 생성**
    
    - **통신**
    
    - **줄 URI**
    
    - **회의 정책**
    
    - **클라이언트 버전 정책**
    
    - **고정 정책**
    
    - **외부 액세스 정책**
    
    - **보관 정책**
    
    - **위치 정책**
    
    - **클라이언트 정책**
    
    기본 기능을 테스트 하려면 **사용자의 SIP URI 생성** 설정 (구성의 다른 옵션)에 대해 선호 하는 옵션을 선택한 다음 그림에 표시 된 대로 **사용**을 클릭 합니다.
    
     ![제어판에서 사용자를 활성화 합니다.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. **사용할 수** 있는 열에 확인 표시가 표시 된 요약 페이지가 표시 되 고 사용자가 설정 되었음을 나타냅니다. **SIP 주소** 열에는 사용자 로그인 구성에 필요한 주소가 표시 됩니다.
    
     ![사용자가 비즈니스용 Skype 서버 제어판에 추가 되었습니다.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. 도메인에 가입 된 컴퓨터와 도메인의 다른 컴퓨터에 있는 다른 사용자에 게 한 명의 사용자를 로그인 합니다.
    
13. 두 클라이언트 컴퓨터 각각에 비즈니스용 Skype 클라이언트를 설치한 다음 두 사용자가 비즈니스용 Skype 서버에 로그인 할 수 있고 서로에 게 인스턴트 메시지를 보낼 수 있는지 확인 합니다.
    

