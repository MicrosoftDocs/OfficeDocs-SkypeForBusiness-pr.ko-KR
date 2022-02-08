---
title: 2016년 8월에 네트워크 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 네트워크 사이트 간 정책을 만들며, 이 정책은 Enterprise Voice 통화 비즈니스용 Skype 서버.
ms.openlocfilehash: 6d3243f2fd3be78228c9bac72219b4906b84ecfb
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387366"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>2016년 8월에 네트워크 비즈니스용 Skype 서버
 
네트워크 사이트 간 정책을 만들며, 이 정책은 Enterprise Voice 통화 비즈니스용 Skype 서버. 
  
네트워크 사이트 간 정책은 사이트 간에 직접 WAN 링크가 있는 사이트 간의 대역폭 제한을 정의합니다.
  
> [!IMPORTANT]
> 네트워크 사이트 간 정책은 두 네트워크 사이트  간에 직접 상호 링크가 있는 경우만 필요합니다.
  
북미 지역의 예 토폴로지에는 리노 사이트와 앨버커키 사이트가 직접 연결됩니다. 이러한 두 사이트에는 적절한 대역폭 정책 프로필을 적용하는 사이트 간 정책이 필요합니다. 다음은 사용자 프로필을 20Mb_Link 예제입니다.
  
### <a name="to-create-a-network-inter-site-policy"></a>네트워크 사이트 간 정책을 만들 수 있습니다.

1. 비즈니스용 Skype 서버 시작 **: 시작,** 모든 **프로그램, 비즈니스용 Skype** **2015** 를 클릭한 다음 관리 **비즈니스용 Skype 서버 클릭합니다**.
    
2. New-CsNetworkInterSitePolicy cmdlet을 실행하여 네트워크 사이트 간 정책을 만들고 직접 교차 링크가 있는 두 사이트에 대해 적절한 대역폭 정책 프로필을 적용합니다. 예를 들어 다음을 실행합니다.
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 필요에 따라 2단계를 반복하여 직접 교차 링크가 있는 모든 네트워크 사이트 쌍에 대한 네트워크 사이트 간 정책을 만들 수 있습니다.
    
## <a name="see-also"></a>참고 항목

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)