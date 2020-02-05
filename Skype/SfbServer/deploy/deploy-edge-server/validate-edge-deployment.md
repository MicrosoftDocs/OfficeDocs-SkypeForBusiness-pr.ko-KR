---
title: 비즈니스용 Skype 서버에서 Edge 배포의 유효성 검사
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: '요약: Edge 서버 또는 Edge 서버 풀이 비즈니스용 Skype 서버에서 작동 하는지 확인 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: c73b77fd0171afe20f9e40b48c47ef4304df4c66
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768301"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 Edge 배포의 유효성 검사
 
**요약:** Edge 서버 또는 Edge 서버 풀이 비즈니스용 Skype 서버에서 작동 하는지 확인 하는 방법에 대해 알아봅니다.
  
Edge 서버 또는 Edge 서버 풀을 배포한 후에는 제대로 작동 하는지 확인 해야 합니다. 여기에는 Edge 환경이 내부 서버에 연결 되어 있는지 확인 하는 데 도움이 되는 몇 가지 내용과 외부 사용자가 Edge를 통해 비즈니스용 Skype 서버 환경에 연결할 수 있습니다.
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a>내부 서버와 Edge 서버 간 연결 확인

Edge 서버 또는 Edge 서버에서 연결에 대 한 유효성 검사를 자동으로 수행 하는 동안에도 계속 해 서 Windows PowerShell을 사용 하 여이를 확인할 수 있습니다. 중앙 관리 저장소가 있는 내부 서버에서 CsManagementStoreReplicationStatus cmdlet을 실행 하거나 비즈니스용 Skype Server Core 구성 요소 (Ocx 점수. msi)가 설치 된 도메인에 연결 된 컴퓨터에 대해 시작 합니다.
  
이 명령을 실행 하면 복제에 대해 True가 아닌 잘못 된 상태가 제공 될 수 있습니다. 이러한 경우 CsManagementStoreReplication cmdlet을 실행 합니다. 복제를 완료 하는 데 시간을 제공 하 고 CsManagementStoreReplicationStatus cmdlet을 다시 실행 합니다.
  
## <a name="verify-connectivity-for-your-external-users"></a>외부 사용자에 대 한 연결 확인

Edge 서버 구성을 확인 하 고 Edge 서버 시나리오에 대 한 올바른 메시지를 보내고 받을 수 있는 기능을 제공 하는 훌륭한 도구가 있습니다. [원격 연결 Anaylzer 사이트](https://testconnectivity.microsoft.com/)입니다. 이 사이트는 Microsoft 지원에서 관리 하 고 유지 관리 하 게 됩니다. 이 도구를 사용 하려면 웹 사이트로 이동 하 여 지침에 따라 적절 한 시나리오를 선택 합니다.
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a>외부 사용자 연결을 테스트할 때 고려해 야 할 사항

외부 사용자 액세스에 대 한 모든 테스트에는 조직에서 지 원하는 각 유형의 내부 사용자가 포함 되어야 하며, 여기에는 다음 중 일부 또는 모두가 포함 될 수 있습니다.
  
- 하나 이상의 페더레이션 도메인에서 사용자를 테스트 하는 것이 좋습니다 (모든 경우에 해당 합니다).
    
- 익명 사용자.
    
- 조직에서 원격으로 비즈니스용 Skype에 로그인 했지만 VPN을 사용 하지 않는 사용자
    
이러한 테스트는 Edge 서버가 다음과 같은지 확인 합니다.
  
- 네트워크 외부의 텔넷 클라이언트를 사용 하 여 필요한 포트를 수신 대기 합니다.
    
  - 예: telnet sip.contoso.com 443
    
  - 배포에 따라 Edge 서버 또는 Edge 서버 풀에서 사용 중인 포트에서 앞의 테스트를 수행 해야 합니다.
    
- 정확한 외부 DNS 확인을 수행 합니다.
    
  - 네트워크 외부에서 Edge 서버 또는 Edge 서버 풀의 각 외부 Fqdn에 대해 ping을 수행 합니다. Ping이 실패 하더라도 이전에 할당 한 IP 주소를 비교할 수 있는 IP 주소가 표시 됩니다.
    

