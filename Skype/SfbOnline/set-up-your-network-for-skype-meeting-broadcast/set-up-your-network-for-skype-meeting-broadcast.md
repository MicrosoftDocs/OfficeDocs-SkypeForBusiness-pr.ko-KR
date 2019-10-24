---
title: Skype 모임 브로드캐스트를 위한 네트워크 설정
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
f1keywords: None
ms.custom:
- SMB
description: 최대 1만 참석자를 대상으로 하는 대규모 온라인 사용자에 게 모임 또는 이벤트를 예약, 생성, 브로드캐스트 하는 데 사용할 수 있는 비즈니스용 Skype Online의 Skype 모임 브로드캐스트 기능에 대해 알아봅니다.
ms.openlocfilehash: 443810772eeb8bf11721825b06b6a87ccb2c97c8
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642750"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a>Skype 모임 브로드캐스트를 위한 네트워크 설정

[Skype 모임 브로드캐스트](enable-skype-meeting-broadcast.md) Skype 모임 브로드캐스트를 사용 하도록 설정한 후에는 네트워크를 구성 해야 합니다. 비즈니스 외부 사용자에 대 한 웹 세미나 진행 및 기타 브로드캐스트를 유지 하려는 경우이 단계를 수행 합니다.

방화벽 구성에 대 한 경험이 없는 경우 [Microsoft 파트너](https://go.microsoft.com/fwlink/?linkid=391089) 를 고용 하 여이 단계를 수행 하는 것이 좋습니다.

이 단계를 건너뛰고 대신 페더레이션에 다른 비즈니스를 추가 하 여 브로드캐스트에 초대할 수 있도록 하려면 [사용자가 외부 비즈니스용 Skype 사용자에 게 연락할 수 있도록 허용](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)의 단계를 따르세요.

## <a name="step-1-set-up-allowed-domains"></a>1 단계: 허용 된 도메인 설정

허용 된 도메인을 설정 하려면 다음 방법 **중 하나** 를 사용 합니다.

## #

 **방법 1: 관리 센터 사용**

1. 관리 센터로 이동한 다음 왼쪽 탐색 창에서 **설정** > **서비스 &amp; 추가 기능**을 클릭 하 고 비즈니스용 **Skype**를 선택 합니다.

2. **외부 공유** 페이지의 **도메인 예외**에서 다음을 **제외한 모든 도메인이 차단 됨**을 선택 하 고 쉼표 (,)로 구분 하 여 다음 도메인을 입력 합니다.

   - noammeetings.lync.com

   - emeameetings.lync.com

   - apacmeetings.lync.com

   - resources.lync.com

3. **저장**을 클릭 합니다.

## #

 **방법 2: Windows PowerShell 사용**

- **시작 메뉴**에서 **Windows PowerShell** 을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 클릭 합니다. **Windows PowerShell** 창에서 각 줄을 입력 하 고 enter 키를 누릅니다.

  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a>2 단계: Skype 모임 브로드캐스트 도메인, Url 및 IP 주소 추가

설치 프로세스의 두 번째 단계는 먼저 필요한 도메인을 추가 하 고 Skype 모임 브로드캐스트에 필요한 IP 주소와 Url을 추가 하는 것입니다.

- 필요한 **비즈니스용 Skype Online 끝점 url 및 IP 주소를 여기에서 필요한 항목을 확인 하 여 추가** [](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)합니다.

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a>하이브리드 배포 및 조직에서 Skype 모임 브로드캐스트 설정

비즈니스용 Skype Online 조직이 있고 Lync Server 2010, Microsoft Lync Server 2013, 비즈니스용 Skype Server 2015 및 사용자가 온라인 및 온-프레미스를 모두 보유 하 고 있는 경우에는 다른 설치 단계가 필요 합니다. 온-프레미스 조직이 비즈니스용 Skype Online과 통신 하 고 모든 사용자가 Skype 모임 브로드캐스트에 참가할 수 있도록 하려면 위의 항목에 추가 하세요. 이러한 요구 사항을 보려면 [Skype 모임 브로드캐스트에 대 한 온-프레미스 배포 구성을](https://go.microsoft.com/fwlink/?LinkId=617070)참조 하세요.

## <a name="related-topics"></a>관련 항목

[Skype 모임 브로드캐스트 사용](enable-skype-meeting-broadcast.md)

[Office 365 Url 및 IP 주소 범위](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[비즈니스용 Skype Online 설정](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



