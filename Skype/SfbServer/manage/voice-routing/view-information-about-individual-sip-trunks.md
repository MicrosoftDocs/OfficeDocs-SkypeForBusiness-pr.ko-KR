---
title: 비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대 한 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버에서는 여러 트렁크를 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이 및 트렁크는 서로 동일 하지 않으며 관리자는 Get-cstrunk cmdlet을 사용 하 여 개별 SIP 트렁크에 대 한 정보를 확인 해야 합니다.
ms.openlocfilehash: c5288e676f546e07504f4d8609fcea63913b6457
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048181"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 개별 SIP 트렁크에 대 한 정보 보기

비즈니스용 Skype 서버에서는 여러 트렁크를 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이와 트렁크는 서로 동일 하지 않으며 관리자가 [get-cstrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet을 사용 하 여 개별 SIP 트렁크에 대 한 정보를 확인 해야 합니다.

Get-cstrunk cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

**모든 SIP 트렁크에 대 한 정보를 보려면**

다음 명령은 조직에서 사용 중인 모든 SIP 트렁크에 대 한 정보를 반환 합니다.

`Get-CsTrunk`

**특정 SIP 트렁크에 대 한 정보를 보려면**

이 명령은 Id가가 pstngateway: 192.168.0.240 인 SIP 트렁크에 대 한 정보만 반환 합니다.

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**풀에 할당 된 모든 SIP 트렁크에 대 한 정보 보기**

이 예에서는 atl-cs-001.litwareinc.com 풀에 할당 된 모든 SIP 트렁크에 대 한 정보를 반환 합니다.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
