---
title: 비즈니스용 Skype 서버에서 개별 SIP trunks에 대 한 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '요약: 비즈니스용 Skype 서버에서 SIP trunks에 대 한 정보를 보는 방법에 대해 알아보세요.'
ms.openlocfilehash: 366e03c1a3ceef345a52bca6e038c9311fcc3003
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001128"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 개별 SIP trunks에 대 한 정보 보기
 
**요약:** 비즈니스용 Skype 서버의 SIP trunks에 대 한 정보를 보는 방법에 대해 알아보세요.
  
SIP trunks는 PSTN (공공 교환 전화 네트워크)과 함께 비즈니스용 Skype 서버와 Voice over IP 전화 네트워크를 연결 하는 데 사용 됩니다. 이전 버전의 제품에서 trunks는 중재 서버에서 PSTN 게이트웨이로 나가는 호출을 라우팅하는 데 사용 되었으며, 각 게이트웨이는 단일 트렁크로 제한 되었습니다. 결과적으로 PSTN 게이트웨이와 SIP 트렁크는 본질적으로 동일 합니다. 관리자는 연결 된 PSTN 게이트웨이에 대 한 정보를 보고 간단히 개별 SIP 트렁크에 대 한 정보를 볼 수 있다는 것을 의미 합니다.
  
그러나 비즈니스용 Skype Server에서는 이제 여러 trunks 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이 및 trunks 더 이상 1이 아닌 것입니다. 다시 말해, 관리자는 개별 SIP 트렁크에 대 한 정보를 볼 수 있도록 새 [CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet을 사용 해야 합니다.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>모든 SIP trunks에 대 한 정보를 보려면

- 다음 명령은 조직에서 사용 중인 모든 SIP trunks에 대 한 정보를 반환 합니다.
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>특정 SIP 트렁크에 대 한 정보 보기

- 이 명령은 Id PstnGateway: 192.168.0.240와 함께 SIP 트렁크에 대 한 정보만 반환 합니다.
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>풀에 할당 된 모든 SIP trunks에 대 한 정보 보기

- 이 예제에서는 풀 atl-cs-001.litwareinc.com에 할당 된 모든 SIP trunks에 대 한 정보가 반환 됩니다.
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
