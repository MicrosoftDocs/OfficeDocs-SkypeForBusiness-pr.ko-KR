---
title: 비즈니스용 Skype 서버에서 네트워크 사이트 간 정책 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 간 정책 만들기
ms.openlocfilehash: dceb48d0e87706d71de8c69b5622fbab468273b4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190446"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 사이트 간 정책 만들기
 
비즈니스용 Skype 서버에서 엔터프라이즈 음성 통화 허용 제어에 사용 되는 네트워크 간 정책 만들기 
  
네트워크 사이트 간 정책은 서로 직접적인 WAN 링크가 있는 사이트 간의 대역폭 제한을 정의 합니다.
  
> [!IMPORTANT]
> 네트워크 간 정책은 두 네트워크 사이트 간에 직접 상호 연결 된 경우에 *만* 필요 합니다.
  
예제 토폴로지 지역에는 Reno 및 Albuquerque 사이트 간의 직접적인 링크가 있습니다. 이러한 두 사이트에는 적절 한 대역폭 정책 프로필을 적용 하는 사이트 간 정책이 필요 합니다. 다음 예에서는 20Mb_Link 프로필을 적용 합니다.
  
### <a name="to-create-a-network-inter-site-policy"></a>네트워크 사이트 간 정책 만들기

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. CsNetworkInterSitePolicy cmdlet을 실행 하 여 네트워크 간 정책을 만들고 직접 교차 링크가 있는 두 사이트에 적절 한 대역폭 정책 프로필을 적용 합니다. 예를 들어 다음을 실행합니다.
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 필요에 따라 2 단계를 반복 하 여 직접 상호 연결 된 모든 네트워크 사이트 쌍에 대 한 네트워크 간 정책을 만듭니다.
    
## <a name="see-also"></a>참고 항목

[새로운 CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[제거-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
