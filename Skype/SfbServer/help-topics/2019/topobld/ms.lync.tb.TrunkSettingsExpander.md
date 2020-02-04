---
title: 트렁크 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: SIP 트렁크에 대한 설정을 편집하거나 수정하려면 다음을 수행합니다.
ms.openlocfilehash: b2401dd561891b5c54f22003b0a29f61933b0277
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687941"
---
# <a name="trunk-settings-expander"></a>트렁크 설정 확장기

SIP 트렁크에 대한 설정을 편집하거나 수정하려면 다음을 수행합니다.

 **트렁크 이름**: 배포의 SIP 트렁크를 고유하게 식별하는 필수 항목입니다.

 **연결된 PSTN 게이트웨이**: 배포에서 정의된 기존 PSTN 게이트웨이를 선택합니다.

 **IP/PSTN 게이트웨이용 수신 대기 포트**: 게이트웨이가 요청에 대해 수신 대기할 TCP/IP 포트를 나타냅니다. 게이트웨이의 공급업체에 따라 필요한 값은 다를 수 있지만 기본값은 포트 5067입니다.

 **SIP 전송 프로토콜**: 사용되는 프로토콜은 TCP 또는 TLS입니다. TLS가 기본값입니다. 게이트웨이가 지원하는 프로토콜에 대해서는 게이트웨이 공급업체 설명서를 참조하세요. 기본값은 TLS이며 게이트웨이에서 TLS를 지원하는 경우 기본값이 보다 안전한 선택으로 간주되어야 합니다.

 **연결 된 중재 서버**: SIP 트렁크와 연결할 수 있도록 배포에서 기존 중재 서버를 선택 합니다.

> [!NOTE]
> 중재 서버에는 루트 트렁크만 연결할 수 있습니다.

 **연결 된 중재 서버 포트**: 필요한 값으로, 중재 서버가 수신 대기 하도록 구성 된 값으로 설정 됩니다.

![트렁크 설정 확장기](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>참고 항목

[SIP 트렁크 배포 검사 목록](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[SIP 트렁크 구성 요소 및 토폴로지](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
