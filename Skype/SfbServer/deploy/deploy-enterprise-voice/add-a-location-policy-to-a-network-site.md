---
title: 비즈니스용 Skype 서버에서 네트워크 사이트에 위치 정책 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 비즈니스용 Skype Server Enterprise Voice의 네트워크 사이트에 E9-1 위치 정책을 할당 합니다.
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768281"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 사이트에 위치 정책 추가
 
비즈니스용 Skype Server Enterprise Voice의 네트워크 사이트에 E9-1 위치 정책을 할당 합니다. 
  
다음 예에서는 비즈니스용 [Skype Server의 위치 정책 만들기](create-location-policies.md) 에 정의 된 **redmond** 위치 정책을 기존 네트워크 사이트에 추가 하는 방법과 **redmond** 위치 정책을 사용 하는 새 네트워크 사이트를 만드는 방법을 보여 줍니다.
  
네트워크 사이트를 사용 하 여 작업 하는 방법에 대 한 자세한 내용은 다음 cmdlet에 대 한 Lync Server 관리 셸 설명서를 참조 하세요.
  
- **새-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **집합-CsNetworkSite**
    
- **CsNetworkSite 사이트 제거**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>기존 네트워크 사이트에 위치 정책을 할당 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 다음 cmdlet을 실행 하 여 기존 네트워크 사이트를 수정 합니다.
    
    **Redmond 태그가 지정** 된 위치 정책을 **redmond**라는 기존 네트워크 사이트에 할당 합니다.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>새 네트워크 사이트에 위치 정책을 할당 하려면

1. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
2. 다음 cmdlet을 실행 하 여 새 네트워크 사이트를 만듭니다.
    
    네트워크 지역에서 새 네트워크 사이트를 만들고 **Redmond** 태그가 지정 된 위치 정책을 할당 합니다.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


