---
title: 새 IP 또는 PSTN 게이트웨이에 대해 루트 트렁크 정의
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
description: 다음을 구성하여 IP 또는 공중 전화망(PSTN)에 대해 루트 트렁크를 정의합니다.
ms.openlocfilehash: 4f437f9536b834b8b8dc69f59702bc77ce968ef2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835388"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a><span data-ttu-id="34e5c-103">새 IP 또는 PSTN 게이트웨이에 대해 루트 트렁크 정의</span><span class="sxs-lookup"><span data-stu-id="34e5c-103">Define the Root Trunk for a New IP or PSTN Gateway</span></span>

<span data-ttu-id="34e5c-104">다음을 구성하여 IP 또는 공중 전화망(PSTN)에 대해 루트 트렁크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34e5c-104">You define the root trunk for the IP or public switched telephone network (PSTN) by configuring the following:</span></span>

- <span data-ttu-id="34e5c-105">**트렁크 이름**: 트렁크와 연결된 정규화된 도메인 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34e5c-105">**Trunk name**: define the fully qualified domain name associated with the trunk</span></span>

- <span data-ttu-id="34e5c-106">**IP/PSTN 게이트웨이용 수신 대기 포트**: 이 트렁크가 수신 대기할 포트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="34e5c-106">**Listening port for IP/PSTN gateway**: define the port that this trunk will listen on</span></span>

- <span data-ttu-id="34e5c-107">**SIP 전송 프로토콜**: 트렁크 요구 사항에 따라 목록에서 **TCP** 또는 **TLS** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="34e5c-107">**SIP Transport Protocol**: select from the list either **TCP** or **TLS**, based on the trunk requirements</span></span>

- <span data-ttu-id="34e5c-108">**연결된 중재 서버:** 배포에서 사용 가능한 중재 서버 목록에서 선택</span><span class="sxs-lookup"><span data-stu-id="34e5c-108">**Associated Mediation Server**: select from the list of available Mediation Servers in your deployment</span></span>

- <span data-ttu-id="34e5c-109">**연결된 중재 서버 포트:** 선택한 중재 서버가 수신하는 포트 정의</span><span class="sxs-lookup"><span data-stu-id="34e5c-109">**Associated Mediation Server port**: define the port that the selected Mediation Server is listening on</span></span>

## <a name="see-also"></a><span data-ttu-id="34e5c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34e5c-110">See also</span></span>

[<span data-ttu-id="34e5c-111">비즈니스용 Skype 서버 2015에서 미디어 우회를 통해 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="34e5c-111">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[<span data-ttu-id="34e5c-112">비즈니스용 Skype 서버 2015에서 미디어 우회 없이 트렁크 구성</span><span class="sxs-lookup"><span data-stu-id="34e5c-112">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[<span data-ttu-id="34e5c-113">SIP 트렁크 지원</span><span class="sxs-lookup"><span data-stu-id="34e5c-113">SIP Trunking Support</span></span>](https://technet.microsoft.com/library/e3042831-e8d8-4ea2-baa2-1a697401ffa0.aspx)
