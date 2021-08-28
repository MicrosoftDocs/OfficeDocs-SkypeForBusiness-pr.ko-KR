---
title: 2013의 네트워크 사이트에 위치 정책을 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: E9-1-1 위치 정책을 사이트의 네트워크 사이트에 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 85a6d589a02c427382c0145a531bcc47ecab703f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612787"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>2013의 네트워크 사이트에 위치 정책을 비즈니스용 Skype 서버
 
E9-1-1 위치 정책을 사이트의 네트워크 사이트에 비즈니스용 Skype 서버 Enterprise Voice. 
  
다음 예에서는 Create [location policies in 비즈니스용 Skype 서버](create-location-policies.md) to an existing network site에 정의된 **Redmond** 위치 정책을 기존 네트워크 사이트에 추가하는 방법과 **Redmond** 위치 정책을 사용하는 새 네트워크 사이트를 만드는 방법을 보여 제공합니다.
  
네트워크 사이트 사용에 대한 자세한 내용은 다음 cmdlet에 대한 Lync Server 관리 셸 설명서를 참조하십시오.
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>기존 네트워크 사이트에 위치 정책을 지정하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 다음 cmdlet을 실행하여 기존 네트워크 사이트를 수정합니다.
    
    **Redmond라는** 기존 네트워크 사이트에 Redmond 태그가 지정된 위치 정책을 **할당합니다.**
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>새 네트워크 사이트에 위치 정책을 지정하려면

1. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
2. 다음 cmdlet을 실행하여 새 네트워크 사이트를 만듭니다.
    
    네트워크 지역에 새 네트워크 사이트를 만들어 태그가 지정된 **Redmond** 위치 정책을 지정합니다.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


