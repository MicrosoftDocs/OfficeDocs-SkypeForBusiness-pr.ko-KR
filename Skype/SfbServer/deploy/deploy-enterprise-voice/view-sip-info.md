---
title: SIP 트렁크 정보 보기 비즈니스용 Skype 서버
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
description: '요약: SIP 트렁크에 대한 정보를 볼 수 있는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: 2f4cc3a7435577d6c9d635a7dc910873b21f9981
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772799"
---
# <a name="skype-for-business-server-view-information-about-individual-sip-trunks"></a>비즈니스용 Skype 서버: 개별 SIP 트렁크에 대한 정보 보기 
 
**요약:** SIP 트렁크에 대한 정보를 볼 수 있는 방법을 비즈니스용 Skype 서버.
  
SIP 트렁크는 PSTN(비즈니스용 Skype 서버 전화망)에 비즈니스용 Skype 서버 음성을 연결하는 데 사용됩니다. 이전 버전의 제품에서는 트렁크를 사용하여 중재 서버에서 PSTN 게이트웨이로 아웃바운드 통화를 라우팅하고 각 게이트웨이는 단일 트렁크로 제한되었습니다. 따라서 PSTN 게이트웨이와 SIP 트렁크는 기본적으로 동일합니다. 관리자는 연결된 PSTN 게이트웨이에 대한 정보를 보기만 하여 개별 SIP 트렁크에 대한 정보를 볼 수 있습니다.
  
그러나 비즈니스용 Skype 서버 단일 PSTN 게이트웨이에 여러 트렁크를 할당할 수 있습니다. 즉, 게이트웨이와 트렁크가 더 이상 동일하지 않습니다. 따라서 관리자는 개별 SIP 트렁크에 대한 정보를 보기 위해 새 [Get-CsTrunk](/powershell/module/skype/get-cstrunk) cmdlet을 사용하여야 합니다.
  
### <a name="to-view-information-for-all-your-sip-trunks"></a>모든 SIP 트렁크에 대한 정보를 확인

- 다음 명령은 조직에서 사용 중이면 모든 SIP 트렁크에 대한 정보를 반환합니다.
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a>특정 SIP 트렁크에 대한 정보를 보기 위해

- 이 명령은 ID가 PstnGateway:192.168.0.240인 SIP 트렁크에 대한 정보만 반환합니다.
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>풀에 할당된 모든 SIP 트렁크에 대한 정보 보기

- 이 예에서는 풀에 할당된 모든 SIP 트렁크에 대한 정보를 atl-cs-001.litwareinc.com.
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
