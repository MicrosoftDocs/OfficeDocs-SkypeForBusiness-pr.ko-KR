---
title: 에지 배포의 유효성을 비즈니스용 Skype 서버
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - Strat_SB_Hybrid
ms.custom: null
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '요약: 에지 서버 또는 에지 서버 풀의 배포가 에지 서버에서 작동하고 있는지 확인하는 비즈니스용 Skype 서버.'
---

# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>에지 배포의 유효성을 비즈니스용 Skype 서버
 
**요약:** 에지 서버 또는 에지 서버 풀의 배포가 에지 서버에서 작동하고 있는지 확인하는 비즈니스용 Skype 서버.
  
에지 서버 또는 에지 서버 풀을 배포한 후 제대로 작동하고 있는지 알아야 합니다. 다음은 에지 환경이 내부 서버에 연결되고 외부 사용자가 에지를 통해 비즈니스용 Skype 서버 수 있는지 확인하는 데 도움이 될 수 있는 몇 가지입니다.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>내부 서버와 에지 서버 간의 연결 확인

에지 서버가 설치될 때 에지 서버 또는 에지 서버 풀에서 연결 유효성 검사가 자동으로 수행되는 동안 에지 서버 또는 에지 서버 풀에서 직접 확인할 수 Windows PowerShell. 중앙 Get-CsManagementStoreReplicationStatus 저장소가 있는 내부 서버 또는 비즈니스용 Skype 서버 핵심 구성 요소(OcsCore.msi)가 설치된 도메인에 가입된 컴퓨터에서 OcsCore.msi 실행합니다.
  
이 명령을 처음 실행하면 복제에 대해 True가 아닌 False 상태가 제공될 수 있습니다. 이 경우 cmdlet을 Invoke-CsManagementStoreReplication 실행합니다. 복제를 완료할 시간을 주었다가 다시 Get-CsManagementStoreReplicationStatus 실행합니다.
  
## <a name="verify-connectivity-for-your-external-users"></a>외부 사용자에 대한 연결 확인

에지 서버 구성을 확인하기 위한 훌륭한 도구와 에지 서버 시나리오에 대한 올바른 메시지를 연결, 보내고 받는 기능을 제공합니다. 원격 연결 아 [나일zer 사이트입니다](https://testconnectivity.microsoft.com/). Microsoft 지원에서 관리 및 유지 관리하는 사이트입니다. 이 도구를 사용하려면 웹 사이트를 찾아 지침에 따라 적합한 시나리오를 선택하세요.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>외부 사용자 연결을 테스트할 때 고려할 문제

외부 사용자 액세스에 대한 모든 테스트에는 조직에서 지원하는 각 내부 사용자 유형(다음 중 하나 또는 모두 포함)이 포함되어야 합니다.
  
- 하나 이상의 페더니트 도메인의 사용자(모두 테스트하는 것이 좋습니다).
    
- 익명 사용자
    
- 조직에서 원격으로 로그인되어 있지만 vpn을 비즈니스용 Skype 사용자입니다.
    
이러한 테스트에서는 에지 서버가 다음인지 여부를 확인할 수 있습니다.
  
- 네트워크 외부의 텔넷 클라이언트를 사용하여 필요한 포트를 수신 대기하는지 여부
    
  - 예: 텔넷 sip.contoso.com 443
    
  - 배포에 따라 에지 서버 또는 에지 서버 풀에서 사용하는 포트에 대해 위의 테스트를 수행해야 합니다.
    
- 정확한 외부 DNS 확인을 수행하는지 여부
    
  - 네트워크 외부에서 에지 서버 또는 에지 서버 풀의 각 외부 FQDNs를 ping합니다. ping이 실패하는 경우에도 이전에 할당한 IP 주소를 비교할 수 있는 IP 주소가 표시됩니다.
    

