---
title: 에지 서버 옵션 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: 에지 풀에 대해 사용하도록 설정할 각 기능을 선택합니다. 기본적으로 에지 풀은 VPN(가상 사설망)을 사용하여 방화벽 외부에서 로그인하는 조직의 원격 사용자를 지원합니다. 또한 다음과 같은 에지 풀 기능 옵션을 사용할 수 있습니다.
ms.openlocfilehash: 0a16c62d4a2f47c94d248d0b43f9598e2f71551e
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798155"
---
# <a name="add-edge-server-options"></a>에지 서버 옵션 추가

에지 풀에 대해 사용하도록 설정할 각 기능을 선택합니다. 기본적으로 에지 풀은 VPN(가상 사설망)을 사용하여 방화벽 외부에서 로그인하는 조직의 원격 사용자를 지원합니다. 또한 다음과 같은 에지 풀 기능 옵션을 사용할 수 있습니다.

- 액세스 에지 서비스, 웹 회의 에지 서비스, A/V 에지 서비스를 비롯한 모든 에지 서비스에 대해 단일 FQDN(정규화된 도메인 이름) 및 IP 주소를 사용합니다. 단일 FQDN 및 IP 주소를 사용하는 옵션을 선택하지 않는 경우 배포 프로세스의 일환으로 이러한 세 가지의 각 에지 서비스에 대해 서로 다른 FQDN 및 IP 주소를 지정해야 합니다. 에지 서비스에 대한 자세한 내용은 계획 설명서에서 [Components Required for External User Access](https://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx)를 참조하세요.

    > [!NOTE]
    > 이 옵션을 선택하는 경우 각 에지 서비스에 대해 서로 다른 포트 번호를 지정해야 합니다(권장 기본 포트 설정: 액세스 에지 서비스의 경우 444, 웹 회의 에지 서비스의 경우 8057, A/V 에지 서비스의 경우 443). 이 옵션을 선택하면 세 가지 서비스 모두에 대해 사용되는 하나의 FQDN을 입력할 수 있기 때문에 구성을 간소화하고 잠재적인 연결 문제를 방지할 수 있습니다.

- 페더레이션에 대한 지원. 지원되는 공용 IM(메신저 대화) 공급자의 사용자를 비롯한 조직 외부의 트러스트된 도메인의 사용자와 내부 사용자 간의 통신을 지원하려는 경우 이 옵션을 선택합니다. 이 옵션을 선택하는 경우 지원할 특정 페더레이션 도메인 및 공용 IM 연결 서비스 공급자에 대한 지원을 구성해야 합니다. 페더레이션 및 기타 외부 사용자 액세스 유형에 대한 지원을 구성하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Configuring Support for External User Access](https://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx)을 참조하세요.

    > [!NOTE]
    > 조직에 있는 단 하나의 프런트 엔드 풀 또는 Standard 에지 서버만 페더레이션을 위해 외부적으로 게시할 수 있습니다. 공용 IM 사용자를 비롯한 페더레이션 사용자에 의한 모든 액세스는 동일한 에지 풀 또는 단일 에지 서버를 통과합니다. 예를 들어 배포에 뉴욕에 배포된 에지 풀 또는 단일 에지 서버와 런던에 배포된 에지 풀 또는 단일 에지 서버가 포함된 경우 뉴욕 에지 풀 또는 단일 에지 서버에서 페더레이션 지원을 사용하도록 설정하면 페더레이션 사용자에 대한 신호 트래픽이 뉴욕 에지 풀 또는 단일 에지 서버를 통과합니다. 이는 런던 페더레이션 사용자를 호출하는 런던 내부 사용자가 A/V 트래픽에 대해 런던 풀 또는 에지 서버를 사용하기는 하지만 런던 사용자와의 통신에도 해당합니다.

- XMPP 페더레이션 사용. 내부 사용자와 트러스트된 XMPP 파트너 간의 통신을 지원하려면 이 옵션을 선택합니다.

초기 토폴로지를 배포할 때 또는 이후에 외부 사용자 액세스에 대한 지원을 추가할 수 있습니다. 기존 토폴로지에 에지 서버를 추가하는 방법에 대한 자세한 내용은 에지 서버 배포 설명서에서 [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)를 참조하세요.


