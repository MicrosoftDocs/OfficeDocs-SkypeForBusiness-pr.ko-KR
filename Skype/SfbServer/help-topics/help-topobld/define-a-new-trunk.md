---
title: 새 트렁크 정의
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
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 다음 정보를 제공하여 새 SIP(Session Initiation Protocol) 트렁크를 정의합니다.
ms.openlocfilehash: bbed07920bdeddb78217e435e8813c89231cdcc9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833048"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="22005-103">새 트렁크 정의</span><span class="sxs-lookup"><span data-stu-id="22005-103">Define a New Trunk</span></span>

<span data-ttu-id="22005-104">다음 정보를 제공하여 새 SIP(Session Initiation Protocol) 트렁크를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="22005-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="22005-105">**트렁크 이름**: 이 트렁크를 식별할 토폴로지의 고유 이름</span><span class="sxs-lookup"><span data-stu-id="22005-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="22005-106">**연결된 PSTN 게이트웨이:** 목록에서 배포 시 배포 및 구성된 PSTN 게이트웨이 선택</span><span class="sxs-lookup"><span data-stu-id="22005-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="22005-107">**IP/PSTN** 게이트웨이용 수신 포트: IP-PBX 또는 PSTN 게이트웨이가 수신하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="22005-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="22005-108">배포에 구성된 다른 모든 트렁크 수신 포트에서 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22005-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="22005-109">**SIP 전송 프로토콜**: TCP 또는 TLS 목록에서 선택</span><span class="sxs-lookup"><span data-stu-id="22005-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="22005-110">**연결된 중재 서버:** 배포에 배포 및 구성된 중재 서버 목록에서 선택</span><span class="sxs-lookup"><span data-stu-id="22005-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="22005-111">연결된 중재 서버 **포트:** 이 SIP 트렁크가 사용할 중재 서버의 TCP 또는 TLS 포트 값으로 포트 값을 설정</span><span class="sxs-lookup"><span data-stu-id="22005-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="22005-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22005-112">See also</span></span>

[<span data-ttu-id="22005-113">비즈니스용 Skype 서버 2015의 M:N 트렁크</span><span class="sxs-lookup"><span data-stu-id="22005-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="22005-114">SIP 트렁크를 구현하는 방법</span><span class="sxs-lookup"><span data-stu-id="22005-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
