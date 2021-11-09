---
title: 에지 서버 옵션 추가
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 에지 풀에 대해 사용하도록 설정할 각 기능을 선택합니다. 기본적으로 에지 풀은 VPN(가상 사설망)을 사용하여 방화벽 외부에서 로그인하는 조직의 원격 사용자를 지원합니다. 다음과 같은 에지 풀 기능 옵션도 있습니다.
ms.openlocfilehash: e9da9c45335cf023dc7da99656fe8a266164efc9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862625"
---
# <a name="add-edge-server-options"></a>에지 서버 옵션 추가

에지 풀에 대해 사용하도록 설정할 각 기능을 선택합니다. 기본적으로 에지 풀은 VPN(가상 사설망)을 사용하여 방화벽 외부에서 로그인하는 조직의 원격 사용자를 지원합니다. 다음과 같은 에지 풀 기능 옵션도 있습니다.

- 액세스 에지 서비스, 웹 회의 에지 서비스 및 A/V 에지 서비스를 비롯한 모든 에지 서비스에 단일 FQDN(정식 도메인 이름) 및 IP 주소 사용 단일 FQDN 및 IP 주소를 사용하는 옵션을 선택하지 않는 경우 배포 프로세스의 일부로 이러한 세 가지 에지 서비스에 대해 각각 별도의 FQDN 및 IP 주소를 지정해야 합니다. 에지 서비스에 대한 자세한 내용은 계획 설명서에서 [Components Required for External User Access을](/previous-versions/office/lync-server-2013/lync-server-2013-components-required-for-external-user-access) 참조하십시오.

    > [!NOTE]
    > 이 옵션을 선택하는 경우 각 에지 서비스에 대해 다른 포트 번호를 지정해야 합니다(권장 기본 포트 설정: 액세스 에지 서비스의 경우 444, 웹 회의 에지 서비스의 경우 8057, A/V 에지 서비스의 경우 443). 이 옵션을 선택하면 세 가지 서비스에 모두 사용되는 하나의 FQDN을 입력할 수 있기 때문에 잠재적인 연결 문제를 방지하고 구성을 단순화할 수 있습니다.

- 페더전 지원. 지원되는 공용 IM(인스턴트 메시징) 공급자의 사용자를 포함하여 조직 외부의 신뢰할 수 있는 도메인에 있는 사용자와 내부 사용자 간의 통신을 지원하려면 이 옵션을 선택합니다. 이 옵션을 선택하는 경우 지원할 특정 페더티된 도메인 및 공용 IM 연결 서비스 공급자에 대한 지원을 구성해야 합니다. 페더링 및 기타 유형의 외부 사용자 액세스에 대한 지원을 구성하는 데 대한 자세한 내용은 에지 서버 배포 설명서에서 [Configuring Support for External User Access을](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-support-for-external-user-access) 참조하십시오.

    > [!NOTE]
    > 조직에 있는 하나의 프런트 엔드 풀 또는 표준 에지 서버만 페더전을 위해 외부에 게시될 수 있습니다. 공용 IM 사용자를 포함하여 페더러티 사용자의 모든 액세스는 동일한 에지 풀 또는 단일 에지 서버를 통과합니다. 예를 들어 배포에 뉴욕에 배포된 에지 풀 또는 단일 에지 서버와 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에서 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통과합니다. 이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.

- XMPP 페더럴을 사용하도록 설정 내부 사용자와 신뢰할 수 있는 XMPP 파트너 간의 통신을 지원하려면 이 옵션을 선택합니다.

초기 토폴로지를 배포할 때 또는 이후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다. 기존 토폴로지에 에지 서버를 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)를 참조하십시오.