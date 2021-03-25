---
title: 에지 설정 확장기
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
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 다음 섹션에서 기존 단일/다중 서버 에지 풀의 설정을 편집할 수 있습니다.
ms.openlocfilehash: 5b4bbb302f76a38a5a485d17ad6df5c0d1db1c6b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119657"
---
# <a name="edge-settings-expander"></a>에지 설정 확장기

다음 섹션에서 기존 단일/다중 서버 에지 풀의 설정을 편집할 수 있습니다.

- 일반 설정

- 다음 홉 선택 설정

- 에지 서버 구성



## <a name="general-settings"></a>일반 설정

에지 서버 풀의 내부 풀 FQDN(정규화된 도메인 이름) 이 설정을 변경하려면 풀의 FQDN을 편집합니다.

Lync Server 2013, Microsoft Lync Server 2010 또는 Microsoft Office Communications Server 2007 R2 트러스트된 파트너와의 페더미스를 설정하려면 이 에지 풀에 페더전 사용(포트 **5061)** 확인란을 선택합니다.

XMPP 페더레이션을 사용하도록 설정하려면 **이 에지 풀에 XMPP 페더레이션 사용** 을 선택합니다.

**내부 구성 복제 포트(HTTPS)** 의 포트 번호를 지정합니다.

## <a name="next-hop-selection-settings"></a>다음 홉 선택 설정

에지 서버에서  내부 인프라와 통신하는 데 사용할 다음 홉 풀을 설정하거나 수정하려면 드롭다운 목록 상자에서 Director, Director 풀, 프런트 엔드 서버 또는 프런트 엔드 서버 풀을 선택합니다. 토폴로지 작성기에서 구성된 Director 또는 프런트 엔드만 선택에 표시됩니다.

## <a name="edge-server-configuration"></a>에지 서버 구성

에지 서버의 **외부 설정** 에 대한 설정을 편집하거나 지정하려면 먼저 SIP 액세스, 웹 회의 및 오디오/비디오 서비스에 서로 다른 IP 주소를 사용할지를 결정해야 합니다.

각각에 대해 서로 다른 IP 주소를 사용하려는 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택합니다. 각 서비스에는 각 서비스에 대해 만들어진 해당 DNS 호스트(A) 레코드가 있어야 합니다.

각 외부 연결 서비스에 대해 FQDN 및 연결된 포트를 지정합니다. 예를 들어 **SIP 액세스** 에서 sip.contoso.com과 연결된 포트 5061을 사용합니다.

> [!IMPORTANT]
> 각 외부 연결 서비스에 대해 서로 다른 FQDN을 선택하는 경우 각 서비스에 각 서비스와 연결된 고유한 포트 값이 있어야 합니다. 기본적으로 SIP는 포트 5061/TLS에 있으며, 웹 회의 에지 서비스는 포트 444/TLS에 있으며, A/V 회의 서버는 포트 443/TLS에 있습니다. 서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.

조직에서 외부 연결 서비스에 단일 FQDN 및 IP 주소를 사용하기로 결정한 경우 **웹 회의와 A/V에 서로 다른 FQDN 및 IP 주소 사용** 확인란을 선택 취소합니다. 그러면 필요한 경우 **SIP 액세스** 풀 FQDN 및 포트 값을 편집할 수 있습니다.

> [!IMPORTANT]
> 서로 다른 FQDN 및 IP 주소 또는 포트 사용을 비롯한 이러한 설정을 변경하는 경우 처음 구성된 값을 사용하는 다른 서비스를 모두 업데이트해야 합니다.

## <a name="see-also"></a>참고 항목

에지 서비스의 설정을 정의 및 구성하는 방법에 대한 자세한 내용은 [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)를 참조하십시오.