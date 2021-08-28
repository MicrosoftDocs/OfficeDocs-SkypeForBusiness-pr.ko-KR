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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 최대 10,000명 Skype 모임 대규모 온라인 비즈니스용 Skype 모임 또는 이벤트를 예약, 제작 및 브로드캐스트할 수 있는 Skype 모임 온라인의 브로드캐스트 기능에 대해 자세히 알아보습니다.
ms.openlocfilehash: 998fbb0a0c077507731d8db09521d49e5c5d635f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594852"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트의 네트워크 설정

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

브로드캐스트 [Skype 모임 브로드캐스트](enable-skype-meeting-broadcast.md) Skype 모임 설정한 후 네트워크를 구성해야 합니다. 비즈니스 외부 사용자에 대한 웨비나 및 기타 브로드캐스트를 보류하려는 경우 이 단계를 합니다.

> [!IMPORTANT]
> 비즈니스용 Skype 온라인은 2021년 7월 31일 사용 중지 중입니다. 그러면 서비스에 대한 액세스가 종료됩니다. 고객이 통신 및 팀워크의 핵심 Microsoft Teams 클라이언트로 업그레이드를 Microsoft 365.

방화벽을 구성하는 데 경험이 없는 경우 이 단계를 위해 [Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) 파트너를 고용하는 것이 좋습니다.

이 단계를 건너뛰고 브로드캐스트에 다른 비즈니스를 추가하여 브로드캐스트에 초대할 수 있도록 다른 비즈니스를 추가하는 대신 사용자가 외부 사용자와 연락하도록 허용의 비즈니스용 Skype [합니다.](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

## <a name="step-1-set-up-allowed-domains"></a>1단계: 허용되는 도메인 설정

다음 **방법** 중 하나를 사용하여 허용되는 도메인을 설정합니다.

### <a name="method-1-use-the-admin-center"></a>방법 1: 관리 센터 사용

1. 관리 센터로 이동한 다음 왼쪽 설정 서비스 추가 기능을 클릭한 다음 을  >  **&amp;** **비즈니스용 Skype.**

2. 도메인 예외 **아래** 외부 공유 페이지에서  **를** 제외한 모든 도메인이 차단된 것을 선택하고 콤마(,)로 구분된 다음 도메인을 입력합니다.

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. **저장** 을 클릭합니다.

### <a name="method-2-use-windows-powershell"></a>메서드 2: Windows PowerShell

- 시작 **메뉴에서** 마우스 **오른쪽 단추로** Windows PowerShell 관리자로 **실행을 클릭합니다.** Windows PowerShell 창에 각 **줄을** 입력하고 Enter를 클릭합니다.

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>2단계: 브로드캐스트 Skype 모임 URL 및 IP 주소 추가

설치 프로세스의 두 번째 단계는 먼저 필요한 도메인을 추가한 다음 브로드캐스트에 필요한 IP 주소 및 URL을 Skype 모임 것입니다.

- **여기서 필요한** 비즈니스용 Skype 온라인 엔드포인트 URL 및 IP 주소를 [추가합니다.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>하이브리드 Skype 모임 조직에서 브로드캐스트 설정

온라인 조직 및 Lync Server 2010, Microsoft Lync Server 2013 및 비즈니스용 Skype 서버 201 비즈니스용 Skype 5의 온-프레미스 배포가 있는 경우 온-프레미스 조직이 온라인과 통신하고 모든 사용자가 브로드캐스트에 참가하도록 허용하기 위해 위의 설정 단계 외에도 수행해야 하는 다른 설정 단계가 Skype 모임. 비즈니스용 Skype 이러한 요구 사항이 어떤지 확인한 경우 브로드캐스트용 프레미스 배포 구성을 [Skype 모임 참조하세요.](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)

## <a name="related-topics"></a>관련 주제

[Skype 모임 브로드캐스트 사용](enable-skype-meeting-broadcast.md)

[Office 365 URL 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[비즈니스용 Skype 온라인 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
