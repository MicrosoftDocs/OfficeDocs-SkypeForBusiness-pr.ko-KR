---
title: 새 트렁크 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 다음 정보를 제공 하 여 새 SIP (세션 초기화 프로토콜) 트렁크를 정의 합니다.
ms.openlocfilehash: 17f6b72f1234813e717cfc72be60bb5f0352134a
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794317"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="656d3-103">새 트렁크 정의</span><span class="sxs-lookup"><span data-stu-id="656d3-103">Define a New Trunk</span></span>

<span data-ttu-id="656d3-104">다음 정보를 제공 하 여 새 SIP (세션 초기화 프로토콜) 트렁크를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="656d3-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="656d3-105">**트렁크 이름**:이 트렁크를 식별 하는 토폴로지의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="656d3-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="656d3-106">**연결 된 Pstn 게이트웨이**: 목록에서 배포에 배포 및 구성한 pstn 게이트웨이를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="656d3-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="656d3-107">IP/PSTN 게이트웨이: IP PBX 또는 PSTN 게이트웨이가 수신 대기 하는 포트 **에 대 한 수신 대기 포트**입니다.</span><span class="sxs-lookup"><span data-stu-id="656d3-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="656d3-108">배포에 구성 된 다른 모든 트렁크 수신 대기 포트에서 고유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="656d3-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="656d3-109">**SIP 전송 프로토콜**: 목록에서 TCP 또는 TLS 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="656d3-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="656d3-110">**연결 된 중재 서버**: 배포에 배포 되 고 구성 되는 중재 서버를 목록에서 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="656d3-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="656d3-111">**연결 된 중재 서버 포트**:이 SIP 트렁크에서 사용할 중재 서버의 TCP 또는 TLS 포트 값과 동일한 포트 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="656d3-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="656d3-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="656d3-112">See also</span></span>

[<span data-ttu-id="656d3-113">M:N 비즈니스용 Skype 서버에서의 트렁크</span><span class="sxs-lookup"><span data-stu-id="656d3-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="656d3-114">SIP 트렁크를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="656d3-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
