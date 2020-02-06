---
title: Lync Server 2010에 대한 Edge 서버 옵션 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 새 Edge 서버 또는 Edge 풀을 정의 하 고 새 서버 또는 풀에 대 한 기능을 정의할 수 있는 기회가 제공 됩니다. 선택할 수 있는 옵션은 다음과 같습니다.
ms.openlocfilehash: 983a8a6e4fdeea34930cc9adf2b2cb29e4c75759
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820990"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Lync Server 2010에 대한 Edge 서버 옵션 추가

새 Edge 서버 또는 Edge 풀을 정의 하 고 새 서버 또는 풀에 대 한 기능을 정의할 수 있는 기회가 제공 됩니다. 선택할 수 있는 옵션은 다음과 같습니다.

- **단일 FQDN과 IP 주소 사용**: 확인란을 선택 하 여 단일 Ipv4 또는 ipv6을 사용 하도록 선택한 경우 (Ipv4 및 ipv6을 모두 사용 하도록 선택 하는 경우) 외부 Edge 인터페이스에 대해 각 IP 주소 유형 중 하나를 정의 해야 합니다.

    > [!IMPORTANT]
    > 이 옵션을 선택 하는 경우 하나의 IP 주소 또는 IPv4 및 IPv6 하나만 사용 하지만 각 Edge 인터페이스에 다른 포트 번호를 할당 해야 합니다.

- **페더레이션 사용 (포트 5061)**: sip (세션 초기화 프로토콜)를 사용 하는 다른 sip 페더레이션, 공급자 또는 호스팅된 서비스를 페더레이션 하려면이 확인란을 선택 합니다.

- **이 edge 풀의 외부 IP 주소는 nat에서 번역 됩니다**. edge 외부 인터페이스에 개인 ip 주소를 사용 하는 경우이 확인란을 선택 하 고, edge 서버 또는 edge 풀을 논리적으로 뒤에 배치 하는 NAT (network address translation) 장치를 제공 합니다.

## <a name="see-also"></a>참고 항목

[외부 사용자 액세스 계획](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[외부 사용자 액세스 배포](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
