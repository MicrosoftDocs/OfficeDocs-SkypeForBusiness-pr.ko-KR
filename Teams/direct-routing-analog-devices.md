---
title: 직접 라우팅-아날로그 장치 연결
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
description: 이 문서에서는 Microsoft 전화 시스템 다이렉트 라우팅으로 아날로그 장치를 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 525e898bd0eafe88d6893249465734d7c33a10b2
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341795"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="61f66-103">전화 시스템 다이렉트 라우팅과 함께 아날로그 장치를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="61f66-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="61f66-104">이 문서에서는 전화 시스템 다이렉트 라우팅과 함께 아날로그 장치를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="61f66-105">아날로그 장치를 직접 라우팅에 연결 하려면, 아날로그 전화 통신 어댑터 (ATA)를 사용 해야 하며,이 어댑터는 인증 된 세션 경계 컨트롤러 (SBC) 공급 업체에서 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="61f66-106">사용자가 아날로그 장치에서 전화를 걸 때 신호 및 미디어는 아날로그 통신 어댑터 (ATA)를 통해 SBC로 흐릅니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="61f66-107">SBC는 내부 라우팅 테이블을 기반으로 Microsoft 팀 끝점 또는 PSTN (공개 통신 네트워크)로 전화를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="61f66-108">장치에서 전화를 걸 때 사용 하는 경로는 디바이스에 대해 생성 된 라우팅 정책에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="61f66-109">다음 다이어그램에서는 + 1425 4XX XX XX와 + 1425 5XX XX XX 사이의 번호로 전화를 걸고 받는 모든 팀이 빨간색 경로 (점선)를 사용 해야 하며 + 1425 4XX XX XX과 (와)를 제외한 다른 숫자와의 모든 PSTN 통화 및 기타 번호를 표시 하도록 직접 라우팅이 구성 되었습니다.  숫자 범위 + 1425 5XX XX XX는 파란색 경로 (실선)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

![직접 라우팅 구성을 보여 주는 다이어그램](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="61f66-111">예: 직접 라우팅을 사용 하 여 아날로그 장치 사용을 구성 하는 방법</span><span class="sxs-lookup"><span data-stu-id="61f66-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="61f66-112">직접 라우팅이 있는 아날로그 장치를 사용 하도록 구성 하려면 아날로그 전화 통신 어댑터를 SBC에 연결 하 고 직접 라우팅과 함께 사용할 수 있도록 SBC를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="61f66-113">이 예제에서는 다음 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="61f66-114">직접 라우팅에 SBC 연결</span><span class="sxs-lookup"><span data-stu-id="61f66-114">Connect the SBC to Direct Routing</span></span>
2. <span data-ttu-id="61f66-115">PSTN 사용 만들기</span><span class="sxs-lookup"><span data-stu-id="61f66-115">Create the PSTN Usage</span></span>
3. <span data-ttu-id="61f66-116">음성 경로를 만들어 PSTN 사용에 연결</span><span class="sxs-lookup"><span data-stu-id="61f66-116">Create a voice route and associate it with the PSTN Usage</span></span>
4. <span data-ttu-id="61f66-117">PSTN 사용에 음성 경로 할당</span><span class="sxs-lookup"><span data-stu-id="61f66-117">Assign the voice route to the PSTN Usage</span></span>
5. <span data-ttu-id="61f66-118">온라인 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="61f66-118">Enable the online user</span></span>
6. <span data-ttu-id="61f66-119">사용자에 게 음성 경로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="61f66-119">Assign the voice route policy to the user</span></span>
7. <span data-ttu-id="61f66-120">아날로그 장치에 대 한 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="61f66-120">Create a voice route for an analog device</span></span>

<span data-ttu-id="61f66-121">ATA를 SBC에 연결 하 고 SBC를 구성 하는 방법에 대 한 자세한 내용은 SBC 제조업체 구성 가이드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61f66-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>
- [<span data-ttu-id="61f66-122">오디오 코드 구성 설명서</span><span class="sxs-lookup"><span data-stu-id="61f66-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="61f66-123">1 단계.</span><span class="sxs-lookup"><span data-stu-id="61f66-123">Step 1.</span></span>  <span data-ttu-id="61f66-124">직접 라우팅에 SBC 연결</span><span class="sxs-lookup"><span data-stu-id="61f66-124">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="61f66-125">다음 명령은 아래와 같이 SBC 연결을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-125">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="61f66-126">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="61f66-126">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="61f66-127">신호 포트 5068</span><span class="sxs-lookup"><span data-stu-id="61f66-127">Signaling port 5068</span></span>
- <span data-ttu-id="61f66-128">미디어 우회 모드</span><span class="sxs-lookup"><span data-stu-id="61f66-128">Media bypass mode</span></span>
- <span data-ttu-id="61f66-129">SBC로 착신 전환 된 통화 기록 정보</span><span class="sxs-lookup"><span data-stu-id="61f66-129">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="61f66-130">P-어설션된-통화와 함께 Id (PAI) 헤더가 전달 됨</span><span class="sxs-lookup"><span data-stu-id="61f66-130">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="61f66-131">2 단계: PSTN 사용 만들기</span><span class="sxs-lookup"><span data-stu-id="61f66-131">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="61f66-132">다음 명령은 빈 PSTN 사용량을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-132">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="61f66-133">온라인 PSTN 사용량은 통화 승인에 사용 되는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-133">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="61f66-134">온라인 PSTN 사용은 온라인 음성 정책을 경로에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-134">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="61f66-135">이 예제에서는 사용 가능한 PSTN 사용량의 현재 목록에 "Interop" 문자열을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-135">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="61f66-136">3 단계: 음성 경로를 만들어 PSTN 사용에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-136">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="61f66-137">이 명령은 숫자 범위 + 1425 XXX XX XX에 대 한 id "아날로그-interop"를 사용 하 여 새 온라인 음성 경로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-137">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="61f66-138">음성 경로는 온라인 게이트웨이 sbc.contoso.com 목록에 적용 되며, 경로를 온라인 PSTN 사용 "Interop"와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-138">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="61f66-139">음성 경로에는 특정 음성 경로를 통해 라우팅되는 전화 번호를 식별 하는 정규식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-139">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="61f66-140">4 단계: PSTN 사용에 대 한 음성 경로 할당:</span><span class="sxs-lookup"><span data-stu-id="61f66-140">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="61f66-141">이 명령은 Id "AnalogInteropPolicy"와 함께 새 사용자 단위 음성 라우팅 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-141">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="61f66-142">이 정책에는 단일 온라인 PSTN 사용 ("Interop")이 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-142">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="61f66-143">5 단계: 온라인 사용자 설정</span><span class="sxs-lookup"><span data-stu-id="61f66-143">Step 5: Enable the online user</span></span>

<span data-ttu-id="61f66-144">이 명령은 Id exampleuser@contoso.com를 사용 하 여 사용자 계정을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-144">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="61f66-145">이 경우에는 음성 메일을 사용 하도록 설정 된 VoIP의 Microsoft 구현 인 Enterprise Voice를 사용 하도록 계정이 수정 되 고이 사용자에 게 번호 + 142억5500만를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-145">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="61f66-146">이 명령은 회사 테 넌 트에서 각 팀 사용자 (ATA 장치 사용자 제외)에 대해 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-146">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="61f66-147">6 단계: 사용자에 게 음성 경로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="61f66-147">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="61f66-148">이 명령은 사용자 단위 온라인 음성 라우팅 정책 AnalogInteropPolicy를 id exampleuser@contoso.com를 사용 하 여 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-148">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="61f66-149">이 명령은 회사 테 넌 트에서 각 팀 사용자 (ATA 장치 사용자 제외)에 대해 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-149">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="61f66-150">7 단계: 아날로그 장치에 대 한 음성 경로 만들기</span><span class="sxs-lookup"><span data-stu-id="61f66-150">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="61f66-151">이 명령은 온라인 게이트웨이 sbc.contoso.com 목록에 적용할 수 있는 숫자 범위 + 1425 4XX XX XX에 대 한 id "아날로그-interop"를 사용 하 여 온라인 음성 경로를 만들고 온라인 PSTN 사용 "Interop"와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-151">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="61f66-152">적절 한 전화 번호 패턴으로 각 아날로그 장치에 대해이 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-152">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="61f66-153">또는 이전 단계 중 하나에서 온라인 음성 경로를 구성 하는 동안 아날로그 장치에 대 한 적절 한 번호 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-153">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="61f66-154">고려 사항</span><span class="sxs-lookup"><span data-stu-id="61f66-154">Considerations</span></span>

- <span data-ttu-id="61f66-155">다른 언급이 없는 한 아날로그 장치는 전화를 걸기 위해 DTMF 번호를 보낼 수 있는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-155">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="61f66-156">예를 들어 아날로그 전화, 팩스 시스템, 간접비 호출기 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-156">For example, analog phones, fax machines, and overhead pagers.</span></span>
- <span data-ttu-id="61f66-157">ATA에 연결 된 아날로그 전화기는 팀에서 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-157">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="61f66-158">팀 사용자는 장치에 연결 된 전화 번호를 수동으로 입력 하 여 해당 장치를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f66-158">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="61f66-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61f66-159">See also</span></span>

[<span data-ttu-id="61f66-160">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="61f66-160">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="61f66-161">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="61f66-161">Configure Direct Routing</span></span>](direct-routing-configure.md)
