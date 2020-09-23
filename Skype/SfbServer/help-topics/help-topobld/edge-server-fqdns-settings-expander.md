---
title: 에지 서버 FQDN 설정 확장기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 에 지 서버에 대 한 외부 설정을 편집 하거나 지정 하려면 먼저 SIP (Session 착수 프로토콜) 액세스, 웹 회의에 지 서비스 및 오디오/비디오에 지 서비스에 대해 별도의 IP 주소를 사용할지를 결정 해야 합니다.
ms.openlocfilehash: f04cdcb16678825d9ab7cc4696c4e649676587b2
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218219"
---
# <a name="edge-server-fqdns-settings-expander"></a>에지 서버 FQDN 설정 확장기

에 지 서버에 대 한 **외부 설정을** 편집 하거나 지정 하려면 먼저 SIP (Session 착수 프로토콜) 액세스, 웹 회의에 지 서비스 및 오디오/비디오에 지 서비스에 대해 별도의 IP 주소를 사용할지를 결정 해야 합니다.

각각에 대해 서로 다른 IP 주소를 사용하려는 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택합니다. 각 서비스에는 각 서비스에 대해 만들어진 해당 DNS(Domain Name System) 호스트(A) 레코드가 있어야 합니다.

각 외부 연결 서비스에 대해 FQDN(정규화된 도메인 이름) 및 연결된 포트를 지정합니다. 예를 들어 **SIP 액세스**에 sip.contoso.com과 연결된 포트 5061을 사용할 수 있습니다.

> [!IMPORTANT]
> 각 외부 연결 서비스에 대해 서로 다른 FQDN을 선택하는 경우 각 서비스에 각 서비스와 연결된 고유한 포트 값이 있어야 합니다. 기본적으로 SIP는 포트 5061/TLS에 있고, 웹 회의 에지 서비스는 포트 444/TLS에 있으며, A/V 회의 에지 서비스는 포트 443/TLS에 있습니다. 서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.

조직에서 외부 연결 서비스에 단일 FQDN 및 IP 주소를 사용하기로 결정한 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택 취소합니다. 그러면 필요한 경우 **SIP 액세스** 풀 FQDN 및 포트 값을 편집할 수 있습니다.

> [!IMPORTANT]
> 서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.

에 지 서비스의 설정을 정의 및 구성 하는 방법에 대 한 자세한 내용은 [Define The Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조 하십시오.


