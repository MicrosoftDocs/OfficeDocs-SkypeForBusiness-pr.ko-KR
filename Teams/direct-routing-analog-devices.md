---
title: 직접 라우팅 - 아날로그 디바이스 연결
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 시스템 직접 라우팅과 함께 아날로그 디바이스를 사용하는 Microsoft 전화 이 문서를 읽어보아야 합니다.
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642098"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="028cf-103">직접 라우팅과 함께 아날로그 전화 시스템 방법</span><span class="sxs-lookup"><span data-stu-id="028cf-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="028cf-104">이 문서에서는 직접 라우팅과 함께 아날로그 전화 시스템 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="028cf-105">직접 라우팅에 아날로그 디바이스를 연결하려면 ATA(Analog Telephony 어댑터)를 사용해야 합니다. 이 어댑터는 인증된 SBC(세션 경계 컨트롤러) 공급업체에서 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="028cf-106">사용자가 아날로그 장치에서 전화를 걸면 ATA(Analog Telephony 어댑터)를 통해 SBC로 신호 및 미디어가 흐르게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="028cf-107">SBC는 내부 라우팅 테이블을 기반으로 Microsoft Teams PSTN(공용 전환 전화 네트워크)으로 호출을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="028cf-108">디바이스가 전화를 걸 때 걸리는 경로는 디바이스에 대해 만든 라우팅 정책에 따라 달라 니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="028cf-109">다음 다이어그램에서 직접 라우팅은 +1425 4XX XX XX 및 +1425 5XX XX XX 사이의 숫자를 Teams 호출할 때 빨간색 경로(점선)를 취해야 하도록 구성됩니다. 줄) 및 번호 범위 +1425 5XX XX XX를 제외한 모든 다른 번호 사이의 숫자와 1425 4XX XX XX 사이의 모든 PSTN 호출은 파란색 경로(단선)를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="028cf-110">![직접 라우팅 구성을 보여주는 다이어그램](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="028cf-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="028cf-111">예: 직접 라우팅을 사용하여 아날로그 디바이스 사용을 구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="028cf-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="028cf-112">직접 라우팅을 사용하여 아날로그 디바이스 사용을 구성하려면 아날로그 전화 어댑터를 SBC에 연결하고 직접 라우팅을 사용하도록 SBC를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="028cf-113">이 예제에서는 다음 단계를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="028cf-114">커넥트 라우팅에 SBC를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="028cf-115">PSTN 사용량을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="028cf-116">음성 경로를 만들고 PSTN 사용량과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="028cf-117">음성 경로를 PSTN 사용량에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="028cf-118">온라인 사용자를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-118">Enable the online user.</span></span>
6. <span data-ttu-id="028cf-119">사용자에게 음성 경로 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="028cf-120">아날로그 디바이스에 대한 음성 경로를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="028cf-121">ATA를 SBC에 연결하고 SBC를 구성하는 방법에 대한 자세한 내용은 SBC 제조업체 구성 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="028cf-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="028cf-122">AudioCodes 구성 설명서</span><span class="sxs-lookup"><span data-stu-id="028cf-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="028cf-123">리본 구성 설명서</span><span class="sxs-lookup"><span data-stu-id="028cf-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="028cf-124">Oracle 구성 설명서</span><span class="sxs-lookup"><span data-stu-id="028cf-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="028cf-125">1단계.</span><span class="sxs-lookup"><span data-stu-id="028cf-125">Step 1.</span></span>  <span data-ttu-id="028cf-126">커넥트 SBC에서 직접 라우팅으로 연결</span><span class="sxs-lookup"><span data-stu-id="028cf-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="028cf-127">다음 명령은 다음과 같이 SBC 연결을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="028cf-128">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="028cf-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="028cf-129">신호 포트 5068</span><span class="sxs-lookup"><span data-stu-id="028cf-129">Signaling port 5068</span></span>
- <span data-ttu-id="028cf-130">미디어 우회 모드</span><span class="sxs-lookup"><span data-stu-id="028cf-130">Media bypass mode</span></span>
- <span data-ttu-id="028cf-131">SBC로 전달된 통화 기록 정보</span><span class="sxs-lookup"><span data-stu-id="028cf-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="028cf-132">호출과 함께 전달된 PAI(PAI) 헤더</span><span class="sxs-lookup"><span data-stu-id="028cf-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="028cf-133">2단계: PSTN 사용량 만들기</span><span class="sxs-lookup"><span data-stu-id="028cf-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="028cf-134">다음 명령은 빈 PSTN 사용량을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="028cf-135">온라인 PSTN 사용량은 호출 권한 부여에 사용되는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="028cf-136">온라인 PSTN 사용량은 온라인 음성 정책을 경로에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="028cf-137">이 예제에서는 사용 가능한 PSTN 사용 현황 목록에 "Interop" 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="028cf-138">3단계: 음성 경로를 만들고 PSTN 사용량과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="028cf-139">이 명령은 숫자 범위 +1425 XXX XX에 대한 ID "analog-interop"을 사용하여 새 온라인 음성 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="028cf-140">음성 경로는 온라인 게이트웨이 목록에 적용될 수 sbc.contoso.com 온라인 PSTN 사용 "Interop"과 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="028cf-141">음성 경로에는 특정 음성 경로를 통해 라우팅될 전화 번호를 식별하는 정규식이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="028cf-142">4단계: PSTN 사용량에 음성 경로를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="028cf-143">이 명령은 ID "AnalogInteropPolicy"를 사용하여 사용자당 새 온라인 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="028cf-144">이 정책은 단일 온라인 PSTN 사용량인 "Interop"을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="028cf-145">5단계: 온라인 사용자 사용</span><span class="sxs-lookup"><span data-stu-id="028cf-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="028cf-146">이 명령은 ID를 사용하여 사용자 계정을 exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="028cf-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="028cf-147">이 경우 계정은 VoIP의 Microsoft 구현인 VoIP를 사용하도록 Enterprise Voice 음성 메일을 사용하도록 수정하고 이 사용자에게 번호 +14255000000000을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="028cf-148">이 명령은 회사 테넌트의 Teams 사용자(ATA 디바이스 사용자 제외)에 대해 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="028cf-149">6단계: 사용자에게 음성 경로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="028cf-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="028cf-150">이 명령은 사용자당 온라인 음성 라우팅 정책 AnalogInteropPolicy를 ID를 사용하여 사용자에게 할당 exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="028cf-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="028cf-151">이 명령은 회사 테넌트의 Teams 사용자(ATA 디바이스 사용자 제외)에 대해 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="028cf-152">7단계: 아날로그 디바이스에 대한 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="028cf-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="028cf-153">이 명령은 온라인 게이트웨이 목록에 적용할 수 있는 번호 범위 +1425 4XX XX XX에 대한 ID "analog-interop"을 사용하여 온라인 음성 경로를 만들고 sbc.contoso.com PSTN 사용 "Interop"과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="028cf-154">이 명령은 적절한 전화 번호 패턴을 사용하여 각 아날로그 디바이스에 대해 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="028cf-155">또는 이전 단계 중 하나에서 온라인 음성 경로를 구성하는 동안 아날로그 디바이스에 대한 적절한 숫자 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="028cf-156">고려 사항</span><span class="sxs-lookup"><span data-stu-id="028cf-156">Considerations</span></span>

- <span data-ttu-id="028cf-157">그렇지 않으면 아날로그 디바이스는 전화를 걸기 위해 DTMF 숫자를 보낼 수 있는 모든 디바이스입니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="028cf-158">예를 들어 아날로그 전화, 팩스 머신 및 오버헤드 페이저를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="028cf-159">ATA에 연결된 아날로그 휴대폰은 ATA에서 검색할 수 Teams.</span><span class="sxs-lookup"><span data-stu-id="028cf-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="028cf-160">Teams 디바이스를 호출하려면 디바이스와 연결된 전화 번호를 수동으로 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="028cf-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="028cf-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="028cf-161">See also</span></span>

[<span data-ttu-id="028cf-162">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="028cf-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="028cf-163">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="028cf-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
