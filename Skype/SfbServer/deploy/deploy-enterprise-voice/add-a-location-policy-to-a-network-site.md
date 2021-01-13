---
title: 비즈니스용 Skype 서버에서 네트워크 사이트에 위치 정책 추가
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 비즈니스용 Skype 서버 2016의 네트워크 사이트에 E9-1-1 위치 정책을 Enterprise Voice.
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804278"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 네트워크 사이트에 위치 정책 추가
 
비즈니스용 Skype 서버 2016의 네트워크 사이트에 E9-1-1 위치 정책을 Enterprise Voice. 
  
다음 예에서는 비즈니스용 [Skype](create-location-policies.md) 서버에서 위치 정책 만들기에 정의된 **Redmond** 위치 정책을 기존 네트워크 사이트에 추가하는 방법과 **Redmond** 위치 정책을 사용하는 새 네트워크 사이트를 만드는 방법을 보여 제공합니다.
  
네트워크 사이트 사용에 대한 자세한 내용은 다음 cmdlet에 대한 Lync Server 관리 셸 설명서를 참조하십시오.
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>기존 네트워크 사이트에 위치 정책을 지정하려면

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 다음 cmdlet을 실행하여 기존 네트워크 사이트를 수정합니다.
    
    **Redmond** 태그가 지정된 위치 정책을 **Redmond라는** 기존 네트워크 사이트에 할당합니다.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>새 네트워크 사이트에 위치 정책을 지정하려면

1. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
2. 다음 cmdlet을 실행하여 새 네트워크 사이트를 만듭니다.
    
    네트워크 지역에 새 네트워크 사이트를 만들어 태그가 지정된 **Redmond** 위치 정책을 지정합니다.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


