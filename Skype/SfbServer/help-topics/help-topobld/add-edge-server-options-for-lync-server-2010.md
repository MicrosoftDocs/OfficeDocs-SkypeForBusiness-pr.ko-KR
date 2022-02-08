---
title: Lync Server 2010용 에지 서버 옵션 추가
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 새 에지 서버 또는 에지 풀을 정의하고 새 서버 또는 풀에 대한 기능을 정의할 수 있는 기회가 표시됩니다. 선택할 수 있는 옵션은 다음과 같습니다.
ms.openlocfilehash: 94d8986a1b5e7317e768de4cb54c84a5b0735a07
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385846"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a>Lync Server 2010용 에지 서버 옵션 추가

새 에지 서버 또는 에지 풀을 정의하고 새 서버 또는 풀에 대한 기능을 정의할 수 있는 기회가 표시됩니다. 선택할 수 있는 옵션은 다음과 같습니다.

- **단일 FQDN 및 IP 주소를 사용합니다.**: 외부 에지 인터페이스에 대해 단일 IPv4 또는 IPv6 주소(IPv4 및 IPv6을 둘 다 사용하려면 각 IP 주소 유형 중 하나를 정의해야 함)와 FQDN(정규화된 도메인 이름)을 사용하려면 확인란을 선택합니다.

    > [!IMPORTANT]
    > 이 옵션을 선택하는 경우 IP 주소를 하나만 사용하거나 IPv4 및 IPv6 주소를 하나씩 사용하지만 각 에지 인터페이스에 대해 서로 다른 포트 번호를 할당해야 합니다.

- **페더레이션 사용(포트 5061)**: SIP(Session Initiation Protocol)를 사용하는 기타 SIP 페더레이션, 공급자 또는 호스트된 서비스와 페더레이션하려는 경우 이 확인란을 선택합니다.

- 이 에지 풀의 외부 IP 주소는 **NAT** 로 변환됩니다. 에지 외부 인터페이스에 대해 개인 IP 주소를 사용하며 에지 서버 또는 에지 풀을 논리적으로 뒤에 두는 NAT(Network Address Translation) 장치를 제공하는 경우 이 확인란을 선택합니다.

## <a name="see-also"></a>참고 항목

[외부 사용자 액세스 계획](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[외부 사용자 액세스 배포](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)