---
title: IP 릴레이 캐나다 사용자 가이드
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: None
f1.keywords:
- NOCSH
ms.custom:
- Legal
hideEdit: true
description: 캐나다에 대한 IP 릴레이 계정을 사용하는 방법
ms.openlocfilehash: b7f276bdf921fdc721ef1df883d3c5d714e4a94f
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238670"
---
# <a name="ip-relay-in-canada---user-guide"></a><span data-ttu-id="665f9-103">캐나다의 IP 릴레이 - 사용자 가이드</span><span class="sxs-lookup"><span data-stu-id="665f9-103">IP Relay in Canada - user guide</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="665f9-104">Microsoft의 IP 메시지 릴레이 서비스에 대한 설명:</span><span class="sxs-lookup"><span data-stu-id="665f9-104">Description of the IP Message Relay service from Microsoft:</span></span>

## <a name="scenario-a"></a><span data-ttu-id="665f9-105">시나리오 A</span><span class="sxs-lookup"><span data-stu-id="665f9-105">Scenario A</span></span>
<span data-ttu-id="665f9-106">청각 장애 또는 음성 장애가 있는 사람이 비장애인에게 연락하고자 하는 경우 특수 웹 기반 클라이언트를 통해 전화 걸기라는 에이전트에 "채팅"합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-106">If a hearing- or voice-impaired person wishes to contact a non-impaired individual, they “chat” via a special web-based client to an agent called a Call Taker.</span></span>

<span data-ttu-id="665f9-107">그런 다음 통화자는 채팅 세션을 통해 청각 장애인 또는 음성 장애인과 통신하고 필요한 경우 캐나다 또는 미국 어디서나 전화 네트워크를 통해 비장애인에게 연락합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-107">The Call Taker then communicates with the hearing- or voice-impaired person via the chat session and contacts the non-impaired person through the telephone network anywhere in Canada or the United States, as required.</span></span>

## <a name="scenario-b"></a><span data-ttu-id="665f9-108">시나리오 B</span><span class="sxs-lookup"><span data-stu-id="665f9-108">Scenario B</span></span>
<span data-ttu-id="665f9-109">비장애인이 등록된 청각 또는 음성 장애 사용자와 대화를 원할 경우 Microsoft에서 제공한 무료 전화 번호를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-109">If a non-impaired person wishes to talk to a registered hearing- or voice-impaired user, they call the toll-free number as provided by Microsoft.</span></span>

<span data-ttu-id="665f9-110">그런 다음 통화 담당자는 비장애인과 대화하고 채팅을 통해 청각 장애인 또는 음성 장애인에게 연락하고 대화를 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-110">The Call Taker then communicates with the non-impaired person and contacts the hearing- or voice-impaired person via chat and communicates back and forth.</span></span>

<span data-ttu-id="665f9-111">청각 장애 또는 음성 장애가 있는 사람이 채팅 프로그램에서 온라인이 아닌 경우, 통화자는 발신자에 의해 요청된 경우 청각 장애인 또는 음성 장애인에게 전자 메일을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-111">Should the hearing- or voice-impaired person not be online in the chat program, if an email address is available the Call Taker will send an email to the hearing- or voice-impaired person, if requested by the caller.</span></span>

## <a name="scenario-c"></a><span data-ttu-id="665f9-112">시나리오 C</span><span class="sxs-lookup"><span data-stu-id="665f9-112">Scenario C</span></span>
<span data-ttu-id="665f9-113">청각 장애인 또는 음성 장애인이 긴급 지원이 필요한 경우 적절한 단추인 911 – 경찰 / 911 – Fire / 911 – 구급차를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-113">If an hearing- or voice-impaired person requires emergency assistance, he or she may select the appropriate button:  911 – Police / 911 – Fire / 911 – Ambulance.</span></span>

<span data-ttu-id="665f9-114">이렇게 하면 북부 IP 릴레이 운영자에게 비상 알림이 전송됩니다. 그러면 이 목적을 위해 설계된 911 계정에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-114">This will send an emergency notification to the Northern IP Relay operators, who will then access the 911 account designed for this purpose.</span></span> <span data-ttu-id="665f9-115">통화 담당자가 자신의 주소를 확인하면 해당 PSAP에 연락하여 필요한 기간 동안 줄에 계속 머무를 것입니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-115">Once the Call Taker has confirmed his or her address, they will contact the appropriate PSAP and stay on the line for as long as required.</span></span>

## <a name="how-to-place-a-text-chat-to-voice-call"></a><span data-ttu-id="665f9-116">음성 통화에 텍스트 채팅을 두는 방법</span><span class="sxs-lookup"><span data-stu-id="665f9-116">How to place a Text chat to Voice call</span></span>

https://aka.ms/IPRelay

<span data-ttu-id="665f9-117">음성 통화에 대한 텍스트를 시작하려면 위의 URL로 이동하고 IP 메시지 릴레이 사용자 이름 및 암호로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-117">To initiate a text to voice call, go to the above URL and log in with your IP Message Relay Username and Password.</span></span>

<span data-ttu-id="665f9-118">로그인하면 화면 왼쪽에 지침이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-118">Once logged in, you will see instructions displayed on the left side of your screen.</span></span>

### <a name="how-to-make-a-text-to-voice-call"></a><span data-ttu-id="665f9-119">음성으로 텍스트를 호출하는 방법:</span><span class="sxs-lookup"><span data-stu-id="665f9-119">How to make a Text to Voice call:</span></span>
1. <span data-ttu-id="665f9-120">화면의 오른쪽 아래 모서리에서 채팅 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="665f9-120">In the lower-right corner of screen, click **Chat**.</span></span>
2. <span data-ttu-id="665f9-121">**IPRelay 사용자를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-121">Click the **IPRelay** user.</span></span>
3. <span data-ttu-id="665f9-122">팝업되는 새 상자 아래쪽에 메시지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-122">In the bottom of the new box that pops up, type your message.</span></span>

### <a name="how-to-receive-a-voice-to-text-call"></a><span data-ttu-id="665f9-123">음성 대 텍스트 통화를 수신하는 방법:</span><span class="sxs-lookup"><span data-stu-id="665f9-123">How to receive a Voice to Text call:</span></span>
- <span data-ttu-id="665f9-124">음성 사용자는 음성을 텍스트 통화로 보내기 위해 IP 메시지 릴레이 사용자 이름을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-124">Voice users will need to know your IP Message Relay Username in order to place a voice to text call.</span></span>
- <span data-ttu-id="665f9-125">음성 사용자는 (866) 660-8613을 호출하여 IP 메시지 릴레이 연산자에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-125">Voice users can call (866) 660-8613 to connect with an IP Message Relay operator.</span></span>
- <span data-ttu-id="665f9-126">통화 또는 채팅을 수신하려면 IP 메시지 릴레이 포털에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-126">You must be logged in to the IP Message Relay portal to receive calls or chats.</span></span>

### <a name="how-to-place-a-911-call"></a><span data-ttu-id="665f9-127">911 호출을 두는 방법:</span><span class="sxs-lookup"><span data-stu-id="665f9-127">How to place a 911 call:</span></span>
<span data-ttu-id="665f9-128">긴급이 있는 경우 화면 아래쪽에 있는 적절한 비상 단추를 선택할 수 있습니다(아래와 같이).</span><span class="sxs-lookup"><span data-stu-id="665f9-128">If you experience an emergency, you may select the appropriate emergency button located at the bottom of your screen (as shown below).</span></span>

![긴급 단추](../images/ip-relay-emergency-buttons.png)

<span data-ttu-id="665f9-130">IP 메시지 릴레이 운영자는 911에 연락하여 주소를 확인하고, 더 이상 필요하지 않고 해당 부서가 해당 위치로 파견될 때까지 다양한 응급 센터에서 번역합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-130">The IP Message Relay Operator will contact 911, confirm your address and translate with various emergency centers until he or she is no longer required, and the appropriate department has been dispatched to your location.</span></span>

> [!WARNING]
> <span data-ttu-id="665f9-131">해당 기관에 연락하여 단순히 테스트로 표시하는 경우에도 이 서비스를 테스트하지 말고 긴급 기관에서 거짓 디스패치 수수료가 청구될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-131">Please do not test this service, as the appropriate agency will be contacted and possibly dispatched even if you indicate it is simply a test, and you may be charged a false dispatch fee from the emergency agency.</span></span>

#### <a name="customer-support"></a><span data-ttu-id="665f9-132">고객 지원:</span><span class="sxs-lookup"><span data-stu-id="665f9-132">Customer Support:</span></span>
<span data-ttu-id="665f9-133">특별 프로젝트 또는 [](mailto:specialprojects@northern911.com) specialprojects@northern911.com (705) 222-1733에 문의해 주세요.</span><span class="sxs-lookup"><span data-stu-id="665f9-133">Please contact Special Projects at [specialprojects@northern911.com](mailto:specialprojects@northern911.com) or (705) 222-1733.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="665f9-134">Northern911은 Microsoft를 대신하여 IP 릴레이 서비스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="665f9-134">Northern911 manages the IP relay service on behalf of Microsoft.</span></span>

## <a name="related-topics"></a><span data-ttu-id="665f9-135">관련 주제</span><span class="sxs-lookup"><span data-stu-id="665f9-135">Related topics</span></span>

[<span data-ttu-id="665f9-136">캐나다의 IP 릴레이 - 등록</span><span class="sxs-lookup"><span data-stu-id="665f9-136">IP Relay in Canada - sign up</span></span>](ip-relay-canada-email-signup.md)






