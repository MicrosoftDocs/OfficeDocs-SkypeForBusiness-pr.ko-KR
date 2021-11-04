---
title: 트렁크 설정 확장기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: SIP 트렁크에 대한 설정을 편집하거나 수정하려면 다음을 수행합니다.
ms.openlocfilehash: ea10af8363cd2298f00d06b09c40f6df97014e48
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774988"
---
# <a name="trunk-settings-expander"></a>트렁크 설정 확장기

SIP 트렁크에 대한 설정을 편집하거나 수정하려면 다음을 수행합니다.

 **트렁크 이름**: 배포의 SIP 트렁크를 고유하게 식별하는 필수 항목입니다.

 **연결된 PSTN 게이트웨이**: 배포에서 정의된 기존 PSTN 게이트웨이를 선택합니다.

 **IP/PSTN 게이트웨이용 수신 대기 포트**: 게이트웨이가 요청에 대해 수신 대기할 TCP/IP 포트를 나타냅니다. 게이트웨이의 공급업체에 따라 필요한 값은 다를 수 있지만 기본값은 포트 5067입니다.

 **SIP 전송 프로토콜**: 사용되는 프로토콜은 TCP 또는 TLS입니다. TLS가 기본값입니다. 게이트웨이가 지원하는 프로토콜에 대해서는 게이트웨이 공급업체 설명서를 참조하십시오. 기본값은 TLS이며 게이트웨이에서 TLS를 지원하는 경우 기본값이 보다 안전한 선택으로 간주되어야 합니다.

 **연결된 중재 서버:** SIP 트렁크와 연결하려면 배포에서 기존 중재 서버를 선택합니다.

> [!NOTE]
> 루트 트렁크만 Lync Server 2010 또는 Lync Server 2013 중재 서버와 연결될 수 있습니다.

 **연결된 중재 서버 포트:** 필수 값으로, 중재 서버가 수신하도록 구성된 값으로 설정됩니다.

![트렁크 설정 확장기.](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>참고 항목

[SIP 트렁크 배포 검사 목록](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[SIP 트렁크에 대한 구성 요소 및 토폴로지](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)