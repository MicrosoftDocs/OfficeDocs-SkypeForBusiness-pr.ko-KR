---
title: 에지 서버 FQDN 설정 확장기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: 에지 서버에 대한 외부 설정을 편집하거나 지정하려면 먼저 SIP(Session Initiation Protocol) 액세스, 웹 회의 에지 서비스 및 오디오/비디오 에지 서비스에 대해 별도의 IP 주소를 사용할지 여부를 결정해야 합니다.
ms.openlocfilehash: d2589ccd8bcd3d7f7bfccd39e3adf726f8839ad8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095563"
---
# <a name="edge-server-fqdns-settings-expander"></a>에지 서버 FQDN 설정 확장기

에지  서버에 대한 외부 설정을 편집하거나 지정하려면 먼저 SIP(Session Initiation Protocol) 액세스, 웹 회의 에지 서비스 및 오디오/비디오 에지 서비스에 대해 별도의 IP 주소를 사용할지 여부를 결정해야 합니다.

각각에 대해 서로 다른 IP 주소를 사용하려는 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택합니다. 각 서비스에는 각 서비스에 대해 만들어진 해당 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.

각 외부 연결 서비스에 대해 FQDN(정규화된 도메인 이름) 및 연결된 포트를 지정합니다. 예를 들어 **SIP 액세스** 에 sip.contoso.com과 연결된 포트 5061을 사용할 수 있습니다.

> [!IMPORTANT]
> 각 외부 연결 서비스에 대해 서로 다른 FQDN을 선택하는 경우 각 서비스에 각 서비스와 연결된 고유한 포트 값이 있어야 합니다. 기본적으로 SIP는 포트 5061/TLS에 있고, 웹 회의 에지 서비스는 포트 444/TLS에 있으며, A/V 회의 에지 서비스는 포트 443/TLS에 있습니다. 서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.

조직에서 외부 연결 서비스에 단일 FQDN 및 IP 주소를 사용하기로 결정한 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택 취소합니다. 그러면 필요한 경우 **SIP 액세스** 풀 FQDN 및 포트 값을 편집할 수 있습니다.

> [!IMPORTANT]
> 서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.

에지 서비스의 설정을 정의 및 구성하는 데 대한 자세한 내용은 [Define Your Edge Topology를 참조하세요.](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)