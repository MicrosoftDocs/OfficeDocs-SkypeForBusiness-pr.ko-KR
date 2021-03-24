---
title: 새 트렁크 정의
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 다음 정보를 제공하여 새 SIP(Session Initiation Protocol) 트렁크를 정의합니다.
ms.openlocfilehash: 540076814d2916f74a5e11be42f99b57711da2b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093276"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="31261-103">새 트렁크 정의</span><span class="sxs-lookup"><span data-stu-id="31261-103">Define a New Trunk</span></span>

<span data-ttu-id="31261-104">다음 정보를 제공하여 새 SIP(Session Initiation Protocol) 트렁크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="31261-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="31261-105">**트렁크 이름:** 이 트렁크를 식별하는 토폴로지의 고유 이름</span><span class="sxs-lookup"><span data-stu-id="31261-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="31261-106">**연결된 PSTN 게이트웨이:** 목록에서 배포에서 배포 및 구성된 PSTN 게이트웨이 선택</span><span class="sxs-lookup"><span data-stu-id="31261-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="31261-107">**IP/PSTN** 게이트웨이용 수신 포트: IP-PBX 또는 PSTN 게이트웨이가 수신하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="31261-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="31261-108">배포에 구성된 다른 모든 트렁크 수신 포트에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31261-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="31261-109">**SIP 전송 프로토콜**: 목록에서 TCP 또는 TLS를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31261-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="31261-110">**연결된 중재 서버**: 배포에 배포 및 구성된 중재 서버 목록에서 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="31261-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="31261-111">**연결된 중재** 서버 포트 : 이 SIP 트렁크에서 사용할 중재 서버의 TCP 또는 TLS 포트 값으로 포트 값을 설정</span><span class="sxs-lookup"><span data-stu-id="31261-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="31261-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31261-112">See also</span></span>

[<span data-ttu-id="31261-113">비즈니스용 Skype 서버의 M:N 트렁크</span><span class="sxs-lookup"><span data-stu-id="31261-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="31261-114">SIP 트렁크를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="31261-114">How do I implement SIP trunking?</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)