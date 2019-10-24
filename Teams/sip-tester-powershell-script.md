---
title: 직접 라우팅 세션 경계 컨트롤러 연결을 테스트 하기 위한 PowerShell 스크립트
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 이 PowerShell 스크립트 샘플을 사용 하 여 Microsoft 팀의 직접 라우팅 세션 경계 컨트롤러 연결을 테스트 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37639501"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="01532-103">직접 라우팅 세션 경계 컨트롤러 연결을 테스트 하기 위한 PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="01532-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="01532-104">SIP 테스터 클라이언트는 Microsoft 팀에서 직접 SBC (라우팅 세션 경계 컨트롤러) 연결을 테스트 하는 데 사용할 수 있는 샘플 PowerShell 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="01532-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="01532-105">이 스크립트는 다이렉트 라우팅이 있는 고객 쌍의 SIP (세션 초기화 프로토콜) 트렁크의 기본 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="01532-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="01532-106">이 스크립트는 SIP 테스트를 test runner에 제출 하 고, 결과를 기다린 다음, 사람이 읽을 수 있는 형식으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="01532-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="01532-107">이 스크립트를 사용 하 여 다음과 같은 시나리오를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01532-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="01532-108">아웃 바운드 및 인바운드 통화</span><span class="sxs-lookup"><span data-stu-id="01532-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="01532-109">동시 연결</span><span class="sxs-lookup"><span data-stu-id="01532-109">Simultaneous ring</span></span>
- <span data-ttu-id="01532-110">미디어 확대</span><span class="sxs-lookup"><span data-stu-id="01532-110">Media escalation</span></span>
- <span data-ttu-id="01532-111">Consultative 전송</span><span class="sxs-lookup"><span data-stu-id="01532-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="01532-112">스크립트 및 문서 다운로드</span><span class="sxs-lookup"><span data-stu-id="01532-112">Download the script and documentation</span></span>

<span data-ttu-id="01532-113">[SIP 테스터 클라이언트 스크립트 및 문서](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="01532-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>