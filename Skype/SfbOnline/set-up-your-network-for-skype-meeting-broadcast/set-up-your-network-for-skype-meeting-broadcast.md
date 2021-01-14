---
title: Skype 모임 브로드캐스트의 네트워크 설정
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 최대 10,000명까지 대규모 온라인 청중에게 모임이나 이벤트를 예약, 생성 및 브로드캐스트할 수 있는 비즈니스용 Skype Online의 Skype 모임 브로드캐스트 기능에 대해 자세히 배워보아야 합니다.
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865162"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트의 네트워크 설정

Skype 모임 [브로드캐스트 Skype](enable-skype-meeting-broadcast.md) 모임 브로드캐스트를 사용하도록 설정한 후 네트워크를 구성해야 합니다. 비즈니스 외부 사용자에 대한 웨비나 및 기타 브로드캐스트를 보유하려는 경우 이 단계를 합니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일 사용이 중지됩니다. 그러면 서비스에 대한 액세스가 종료됩니다. Microsoft 365에서 커뮤니케이션 및 팀워크를 위한 핵심 클라이언트인 Microsoft Teams로 업그레이드하는 것이 권장됩니다.

방화벽 구성에 경험이 없는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 좋습니다.

이 단계를 건너뛰고 다른 비즈니스를 브로드캐스트에 초대할 수 있도록 페더러에 다른 비즈니스를 추가하기 위해 사용자가 외부 비즈니스용 Skype 사용자에게 연락할 수 있도록 허용의 [단계를 따릅니다.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>1단계: 허용되는 도메인 설정

다음 **방법** 중 하나를 사용하여 허용되는 도메인을 설정합니다.

## #

 **방법 1: 관리 센터 사용**

1. 관리 센터로 이동한 다음 왼쪽으로 이동하여 **설정** 서비스 추가 기능을 클릭한 다음 비즈니스용  >  **&amp;** **Skype를 선택합니다.**

2. 도메인 **예외의** 외부 공유 페이지에서 모든 도메인이 차단된 것을 선택하고 **다음** 도메인을 콤마(,)로 구분하여 입력합니다.

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. **저장** 을 클릭합니다.

## #

 **방법 2: 다음 Windows PowerShell**

- 시작 **메뉴에서** 마우스 오른쪽 **단추로** Windows PowerShell 관리자 **권한으로 실행을 클릭합니다.** Windows PowerShell **각** 줄을 입력하고 Enter를 누르십시오.

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>2단계: Skype 모임 브로드캐스트 도메인, URL 및 IP 주소 추가

설치 프로세스의 두 번째 단계는 먼저 필요한 도메인을 추가한 다음 Skype 모임 브로드캐스트가 작동하기 위해 필요한 IP 주소와 URL을 추가하는 것입니다.

- **여기에 필요한 비즈니스용 Skype Online** 엔드포인트 URL 및 IP 주소를 [추가합니다.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>하이브리드 배포 및 조직에서 Skype 모임 브로드캐스트 설정

비즈니스용 Skype Online 조직과 Lync Server 2010, Microsoft Lync Server 2013 및 비즈니스용 Skype Server 2015의 온-프레미스 배포가 있으며 사용자가 온라인 및 온-프레미스 모두에 있는 경우, 온-프레미스 조직이 비즈니스용 Skype Online과 통신하고 모든 사용자가 Skype 모임 브로드캐스트에 참가할 수 있도록 하기 위해 위의 설정 단계 외에도 해야 하는 다른 설정 단계가 있습니다. 이러한 요구 사항에 대한 자세한 내용은 Skype 모임 브로드캐스트에 대한 프레미스 배포 [구성을 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=617070)

## <a name="related-topics"></a>관련 항목

[Skype 모임 브로드캐스트 사용](enable-skype-meeting-broadcast.md)

[Office 365 URL 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



