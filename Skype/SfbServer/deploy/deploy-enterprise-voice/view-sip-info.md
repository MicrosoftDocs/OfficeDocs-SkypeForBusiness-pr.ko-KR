---
title: 비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대한 정보 보기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: '요약: 비즈니스용 Skype 서버에서 SIP 트렁크에 대한 정보를 보는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 29a5a025589f4df7d99b8bf708bf8bd67d0f138f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830528"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대한 정보 보기
 
**요약:** 비즈니스용 Skype 서버에서 SIP 트렁크에 대한 정보를 보는 방법을 알아보습니다.
  
SIP 트렁크는 비즈니스용 Skype 서버 Voice over IP 전화 네트워크를 PSTN(Public Switched Telephone Network)에 연결하는 데 사용됩니다. 이전 버전의 제품에서는 트렁크가 중재 서버에서 PSTN 게이트웨이로 아웃바운드 통화를 라우팅하는 데 사용되어 각 게이트웨이가 단일 트렁크로 제한되었습니다. 따라서 PSTN 게이트웨이와 SIP 트렁크는 기본적으로 동일합니다. 관리자는 연결된 PSTN 게이트웨이에 대한 정보를 보기만 하여 개별 SIP 트렁크에 대한 정보를 볼 수 있습니다.
  
그러나 비즈니스용 Skype 서버에서는 이제 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크가 더 이상 같지 않습니다. 따라서 관리자는 새 [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet을 사용하여 개별 SIP 트렁크에 대한 정보를 보아야 합니다.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>모든 SIP 트렁크에 대한 정보를 확인

- 다음 명령은 조직에서 사용 하는 모든 SIP 트렁크에 대 한 정보를 반환 합니다.
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>특정 SIP 트렁크에 대한 정보를 보기 위해

- 이 명령은 ID가 PstnGateway:192.168.0.240인 SIP 트렁크에 대한 정보만 반환합니다.
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>풀에 할당된 모든 SIP 트렁크에 대한 정보 보기

- 이 예제에서는 풀에 할당된 모든 SIP 트렁크에 대한 정보를 atl-cs-001.litwareinc.com.
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
