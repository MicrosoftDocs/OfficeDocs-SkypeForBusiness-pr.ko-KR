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
description: 최대 10,000명에 달하는 대규모 온라인 대상에게 모임 또는 이벤트를 예약, 생성 및 브로드캐스트할 수 있는 비즈니스용 Skype Online의 Skype 모임 브로드캐스트 기능에 대해 자세히 알아보습니다.
ms.openlocfilehash: 513b6f8d677550557293855389eff29dc61c21c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106514"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트의 네트워크 설정

Skype 모임 [브로드캐스트 Skype](enable-skype-meeting-broadcast.md) 모임 브로드캐스트를 사용하도록 설정한 후 네트워크를 구성해야 합니다. 비즈니스 외부 사용자에 대한 웨비나 및 기타 브로드캐스트를 보류하려는 경우 이 단계를 합니다.

> [!IMPORTANT]
> 비즈니스용 Skype Online이 2021년 7월 31일 사용 중지 중입니다. 그러면 서비스에 대한 액세스가 종료됩니다. 고객이 Microsoft 365에서 통신 및 팀워크의 핵심 클라이언트인 Microsoft Teams로 업그레이드를 시작하는 것이 권장됩니다.

방화벽을 구성하는 데 경험이 없는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 좋습니다.

이 단계를 건너뛰고 브로드캐스트에 초대할 수 있도록 페더연맹에 다른 비즈니스를 추가하기 위해 사용자가 외부 [비즈니스용 Skype](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)사용자에 문의하도록 허용의 단계를 따릅니다.

## <a name="step-1-set-up-allowed-domains"></a>1단계: 허용되는 도메인 설정

다음 **방법** 중 하나를 사용하여 허용되는 도메인을 설정합니다.

## #

 **방법 1: 관리 센터 사용**

1. 관리 센터로 이동한 다음 왼쪽 해군에서 **설정** 서비스 추가 기능을 클릭한 다음  >  **&amp;** **비즈니스용 Skype 를 선택합니다.**

2. 도메인 예외 **아래** 외부 공유 페이지에서  **를** 제외한 모든 도메인이 차단된 것을 선택하고 콤마(,)로 구분된 다음 도메인을 입력합니다.

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. **저장** 을 클릭합니다.

## #

 **방법 2: Windows PowerShell**

- 시작 **메뉴에서** 마우스 오른쪽 **단추로** Windows PowerShell 관리자로 **실행을 클릭합니다.** Windows PowerShell 창에 각 **줄을** 입력하고 Enter를 클릭합니다.

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

설치 프로세스의 두 번째 단계는 먼저 필요한 도메인을 추가한 다음 Skype 모임 브로드캐스트가 작동하기 위해 필요한 IP 주소 및 URL을 추가하는 것입니다.

- **여기에 필요한** Skype Online 엔드포인트 URL 및 IP 주소를 [추가합니다.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>하이브리드 배포 및 조직에서 Skype 모임 브로드캐스트 설정

비즈니스용 Skype Online 조직과 Lync Server 2010, Microsoft Lync Server 2013 및 비즈니스용 Skype Server 2015의 온-프레미스 배포가 있는 경우 온-프레미스 조직이 비즈니스용 Skype Online과 통신할 수 있도록 설정하고 모든 사용자가 Skype 모임 브로드캐스트에 참가할 수 있도록 하기 위해 위의 설정 단계 외에도 해야 할 다른 설정 단계가 있습니다. 이러한 요구 사항이 무엇이고 Skype 모임 브로드캐스트에 대한 프레미스 배포 [구성을 참조하세요.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)

## <a name="related-topics"></a>관련 항목

[Skype 모임 브로드캐스트 사용](enable-skype-meeting-broadcast.md)

[Office 365 URL 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)