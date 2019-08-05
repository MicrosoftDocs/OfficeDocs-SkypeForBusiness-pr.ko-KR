---
title: 비즈니스용 Skype 서버에서 개별 SIP trunks에 대 한 정보 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 비즈니스용 Skype 서버에서 여러 trunks 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이 및 trunks는 서로 동일 하지 않으며, 관리자는 CsTrunk cmdlet을 사용 하 여 개별 SIP 트렁크에 대 한 정보를 확인 해야 합니다.
ms.openlocfilehash: f9199936dd4c9580c95c8b9708df04dcac13e1e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186999"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 개별 SIP trunks에 대 한 정보 보기

비즈니스용 Skype 서버에서 여러 trunks 단일 PSTN 게이트웨이에 할당할 수 있습니다. 즉, 게이트웨이 및 trunks는 서로 동일 하지 않으며, 관리자가 [CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet을 사용 하 여 개별 SIP 트렁크에 대 한 정보를 확인 해야 합니다.

CsTrunk cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

**모든 SIP trunks에 대 한 정보를 보려면**

다음 명령은 조직에서 사용 중인 모든 SIP trunks에 대 한 정보를 반환 합니다.

`Get-CsTrunk`

**특정 SIP 트렁크에 대 한 정보 보기**

이 명령은 Id PstnGateway: 192.168.0.240와 함께 SIP 트렁크에 대 한 정보만 반환 합니다.

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

**풀에 할당 된 모든 SIP Trunks에 대 한 정보 보기**

이 예제에서는 풀 atl-cs-001.litwareinc.com에 할당 된 모든 SIP trunks에 대 한 정보가 반환 됩니다.

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
