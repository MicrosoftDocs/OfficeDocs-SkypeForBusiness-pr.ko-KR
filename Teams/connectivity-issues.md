---
title: Teams 클라이언트 연결 문제 해결
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 주로 방화벽 또는 프록시 연결에서 발생하는 Microsoft Teams 클라이언트의 연결 문제 해결 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 59041734887a667eca325a3d2650425d6d336b78
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918544"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="484e1-103">Microsoft Teams 클라이언트의 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="484e1-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="484e1-104">Microsoft Teams 클라이언트에서 발견되는 대부분의 문제는 방화벽 또는 프록시 연결 문제로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="484e1-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="484e1-105">방화벽 또는 프록시에서 필수 URL, IP 주소 및 포트가 열려 있는지 확인하면 불필요한 문제 해결을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="484e1-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="484e1-106">Microsoft Teams에 필요한 URL 및 IP에 대한 자세한 내용은 [Microsoft 365 및 Office 365 URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 및 IP 주소 지원 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="484e1-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="484e1-107">다음 시나리오는 방화벽에서 특정 URL 및 포트가 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="484e1-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="484e1-108">인증</span><span class="sxs-lookup"><span data-stu-id="484e1-108">Authentication</span></span>

- <span data-ttu-id="484e1-109">Microsoft Teams 클라이언트 연결</span><span class="sxs-lookup"><span data-stu-id="484e1-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="484e1-110">공동 작업</span><span class="sxs-lookup"><span data-stu-id="484e1-110">Collaboration</span></span>

- <span data-ttu-id="484e1-111">미디어</span><span class="sxs-lookup"><span data-stu-id="484e1-111">Media</span></span>

- <span data-ttu-id="484e1-112">공유 서비스</span><span class="sxs-lookup"><span data-stu-id="484e1-112">Shared Services</span></span>

- <span data-ttu-id="484e1-113">타사 통합</span><span class="sxs-lookup"><span data-stu-id="484e1-113">Third Party Integration</span></span>

- <span data-ttu-id="484e1-114">비즈니스용 Skype 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="484e1-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="484e1-115">비즈니스용 Skype 클라이언트 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="484e1-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="484e1-116">Teams가 오프라인 상태이거나 대역폭이 낮은 경우</span><span class="sxs-lookup"><span data-stu-id="484e1-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="484e1-117">다행히 오프라인 상태이거나 대역폭이 낮은 조건에서 실행되는 경우에도 Teams가 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="484e1-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="484e1-118">Teams는 기존 채팅을 위해 보내지 않은 모든 메시지를 저장하고(최대 24시간 동안) 다시 온라인이 되자마자 해당 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="484e1-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="484e1-119">24시간 이상 오프라인 상태인 경우 Teams에서 보내지 않은 메시지를 다시 보내거나 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="484e1-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="484e1-120">이 기능을 새 채팅에 추가하기 위해 작업 중입니다. 사용 가능한 경우 이 설명서를 업데이트할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="484e1-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="484e1-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="484e1-121">Related topics</span></span>

[<span data-ttu-id="484e1-122">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="484e1-122">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
